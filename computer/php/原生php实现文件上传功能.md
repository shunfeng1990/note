# 原生php实现文件上传功能

```php
<?php 
	
	//print_r($_FILES);

	//文件存储位置
	$destination = 'uploads/';

	//限制上传文件大小
	$maxsize = 500*1024; //500KB
	if ($_FILES['pic']['size'] > $maxsize) {
		echo '图片大小超出限制';
		exit;
	}

	//分目录存储上传的文件
	$sub_path = date('Ymd').'/';
	if (!is_dir($destination.$sub_path)) {
		mkdir($destination.$sub_path,0777,true);
	}
	$destination .= $sub_path;
	//文件取一个唯一名字
	$filename = uniqid('goods_',true);
	$ext = strrchr($_FILES['pic']['name'], '.');
	$new_filename = $filename.$ext;
	$destination .= $new_filename;

	//允许上传的类型
	$allow_type = array('image/jpeg','image/jpg','image/png','image/gif');
	$true_type = $_FILES['pic']['type'];
	if (!in_array($true_type, $allow_type)) {
		echo '不支持该文件类型';
		exit;
	}
	
	$finfo = new finfo(FILEINFO_MIME_TYPE);
	$type = $finfo->file($_FILES['pic']['tmp_name']);
	if (!in_array($type,$allow_type)) {
		echo '不支持该文件类型';
		exit;
	}
	//移动文件
	if (move_uploaded_file($_FILES['pic']['tmp_name'], $destination)) {
		echo '上传成功'.'<br>';
		echo '图片路径：' . $sub_path.$new_filename;
	}else{
		echo '上传失败';
	}

 ?>
```

