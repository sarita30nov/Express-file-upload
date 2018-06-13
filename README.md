Express js File Upload Code 


var storage = multer.diskStorage({
  destination: function (req, file, cb) {
    cb(null, './public') //Destination folder
  },
  filename: function (req, file, cb) {
    cb(null, file.originalname) //File name after saving
  }
})

var upload = multer({ storage: storage })



app.post('/photo', upload.single('file'),  function(req, res, next)
{
	console.log(req.file);
	console.log(req.body);
	res.render('user/photo', {
        title: 'Upload Photo',
    })
})



<form action="/users/photo" method="post" name="form1" enctype="multipart/form-data">
		name: <input type="text" name="title">
		<br/><br/>
	  Profile picture  <input type="file" name="file">
		<br/><br/>
		<input type="submit" value="Upload">

</form>

Helpfull link

https://github.com/expressjs/multer