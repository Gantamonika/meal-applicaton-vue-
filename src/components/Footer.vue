
<template>
<head>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.1.3/css/bootstrap.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.9.0/css/all.min.css">


</head>
<footer id="footer" class=" text-white d-flex-column text-center">
  <hr class="mt-0">
  
  <div class="text-center">
    <h4>You can find us at</h4>
    <ul class="list-unstyled list-inline">
      <li class="list-inline-item">
        <a href="#!" class="sbtn btn-large mx-1" title="Facebook" >
          <i class="fab fa-facebook-square fa-2x " style="color:white"></i>
        </a>
      </li>
      <li class="list-inline-item">
        <a href="#!" class="sbtn btn-large mx-1" title="Linkedin">
          <i class="fab fa-linkedin fa-2x" style="color:white"></i>
        </a>
      </li>
      <li class="list-inline-item">
        <a href="#!" class="sbtn btn-large mx-1" title="Twitter">
          <i class="fab fa-twitter-square fa-2x" style="color:white"></i>
        </a>
      </li>
      <li class="list-inline-item">
        <a href="#!" class="sbtn btn-large mx-1" title="Youtube">
          <i class="fab fa-youtube-square fa-2x" style="color:white"></i>
        </a>
      </li>
    </ul>
  </div>
  <hr class="mb-0">
  <div class="container text-left text-md-center">
    <div class="row">
      <div class="col-md-2 mx-auto shfooter">
        <router-link to="/" class="my-2 font-weight-bold d-none d-md-block si" >Home</router-link> 
        <div class="d-md-none title" data-target="#Home" data-toggle="collapse">
          <div class="mt-3 font-weight-bold">Home
            <div class="float-right navbar-toggler">
              <i class="fas fa-angle-down"></i>
              <i class="fas fa-angle-up"></i>
            </div>
          </div>
        </div>
      </div>

      <div class="col-md-2 mx-auto shfooter">
        <h4 class="my-2 font-weight-bold d-none d-md-block" style="color:black">About</h4>
        <div class="d-md-none title" data-target="#About" data-toggle="collapse">
          <div class="mt-3 font-weight-bold">About
            <div class="float-right navbar-toggler">
              <i class="fas fa-angle-down"></i>
              <i class="fas fa-angle-up"></i>
            </div>
          </div>
        </div>
        <ul class="list-unstyled collapse" id="About">
          <li>About</li>
          <li><a href="#">Careers</a></li>
          <li><a href="#">Support</a></li>
          <li><a href="#">Pricing</a></li>
          <li><a href="#">FAQ</a></li>
        </ul>
      </div>
      
      <hr class="clearfix w-100 d-md-none mb-0">
      <div class="col-md-2 mx-auto shfooter">
        <h4 class="my-2 font-weight-bold d-none d-md-block"  style="color:black">Get Help</h4>
        <div class="d-md-none title" data-target="#Get-Help" data-toggle="collapse">
          <div class="mt-3 font-weight-bold">Get Help
            <div class="float-right navbar-toggler">
              <i class="fas fa-angle-down"></i>
              <i class="fas fa-angle-up"></i>
            </div>
          </div>
        </div>
        <ul class="list-unstyled collapse" id="Get-Help">
          <li><a href="#" target="_blank">Help Center</a></li>
          <li><a href="#">Contact Us</a></li>
          <li><a href="#">Privacy Policy</a></li>
          <li><a href="#">Terms</a></li>
          <li><a href="#">Login</a></li>
        </ul>
      </div>
    </div>
  </div>
  <hr class="mb-0">
  <div class="py-3 text-center">
    Copyright © 2022
  </div>
</footer>
<h5 class="resize">
  <i class="fas fa-angle-double-left"></i>
  Resize screen
  <i class="fas fa-angle-double-right"></i></h5>


</template>
<style>
a {
  color: black !important;
}
.shfooter .collapse {
  display: inherit;
}
@media (max-width: 767px) {
  .shfooter ul {
    margin-bottom: 0;
  }
 
  .shfooter .collapse {
    display: none;
  }
 
  .shfooter .collapse.show {
    display: block;
  }
 
  .shfooter .title .fa-angle-up,
  .shfooter .title[aria-expanded="true"] .fa-angle-down {
    display: none;
  }
 
  .shfooter .title[aria-expanded="true"] .fa-angle-up {
    display: block;
  }
 
  .shfooter .navbar-toggler {
    display: inline-block;
    padding: 0;
  }
}

 
.resize {
  text-align: center;
}
.resize {
  margin-top: 3rem;
  font-size: 1.25rem;
}
/*RESIZESCREEN ANIMATION*/
.fa-angle-double-right {
  animation: rightanime 1s linear infinite;
}
 
.fa-angle-double-left {
  animation: leftanime 1s linear infinite;
}
@keyframes rightanime {
  50% {
    transform: translateX(10px);
    opacity: 0.5;
  }
  100% {
    transform: translateX(10px);
    opacity: 0;
  }
}
@keyframes leftanime {
  50% {
    transform: translateX(-10px);
    opacity: 0.5;
  }
  100% {
    transform: translateX(-10px);
    opacity: 0;
  }
}
.text-white{
  background-color: #e91e63 ;
}
h5{
  font-size: 2px;
}
.si{
  font-weight: 100%;
}
</style>