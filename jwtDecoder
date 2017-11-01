const jwt = require('njwt');
const express = require('express');
const bodyParser = require('body-parser')
var app = express()
var signKey = 'abcdefghijklmnopqrstuvwxyzabcdef';
app.use(bodyParser.urlencoded({ extended: true }))

app.post("/", function(req, res){
var token=null;
if(req.query)
{
   token = req.query.Analytics; 
}

if(token === null){
    console.log('This is not valid token');
}
else
{
    var jwtverified = jwt.verify(token,signKey, function(err,verifiedJwt){
  if(err){
    console.log(err); // Token has expired, has been tampered with, etc
  }else{
    console.log(verifiedJwt);
    // Will contain the header and body
  }
});
}
}).on("error", function(e){
  console.log("Got error: " + e.message);
});

// Tell our app to listen on port 8080
app.listen(8080, function (err) {
  if (err) {
    throw err
  }
console.log('Server started on port 8080')
})
