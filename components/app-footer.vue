<template>
    <!--start main-footer-->
    <div class="main-footer">
        <div class="container">
            <div class="on-touch">
                <div class="row">
                    <div class="col-md-8 col-12">
                        <p class="">Be On Touch With Us</p>
                    </div>
                    <div class="col-md-4 col-12">
                        <input type="text" placeholder="Enter Your Email">
                        <a href="#" class="text-center"><i class="fas fa-long-arrow-alt-right"></i></a>
                    </div>
                </div>
            </div>

            <!--start foter-->
            <div class="foter">
                <div class="row">
                    <div class="col-md-6 col-lg-3 col-12">

                        <img src="images/logo.svg">

                    </div>

                    <div class="col-md-6 col-lg-3 col-12">
                        <h4>Useful links</h4>
                        <ul>
                            <li><a href="#">About Us</a></li>
                            <li><a href="#">Contact Us</a></li>
                            <li><a href="#">Projects</a></li>
                            <li><a href="#">Services</a></li>
                            <li><a href="#">Blog</a></li>
                        </ul>

                    </div>

                    <div class="col-md-6 col-lg-3 col-12">
                        <h4>Information</h4>
                        <ul>
                            <li><a href="#">Help & Support</a></li>
                            <li><a href="#">Pravicy & Policy</a></li>
                            <li><a href="#">Pricing</a></li>
                            <li><a href="#">Terms</a></li>
                            <li><a href="#">Condition</a></li>
                        </ul>

                    </div>

                    <div class="col-md-6 col-lg-3 col-12 det">
                        <h4>Contacts</h4>
                        <div>
                            <div class="row">
                                <div class="col-1">
                                    <span><i class="fas fa-location-arrow"></i></span>

                                </div>
                                <div class="col-8">
                                    <p>
                                        Someone@Gmail.Com
                                    </p>

                                    <p>
                                        Someone@Gmail.Com
                                    </p>

                                </div>
                            </div>
                        </div>

                        <div>
                            <div class="row">
                                <div class="col-1">
                                    <span><i class="fas fa-phone-volume"></i></span>

                                </div>
                                <div class="col-8">
                                    <p>
                                        +2055254545155
                                    </p>

                                    <p>
                                        +555452550220
                                    </p>

                                </div>
                            </div>
                        </div>

                        <div>
                            <div class="row">
                                <div class="col-1">
                                    <span><i class="fas fa-map-marker-alt"></i></span>

                                </div>
                                <div class="col-10">
                                    <p>
                                        Egypt,Mansoura 26 El-Magzer ST.
                                    </p>



                                </div>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
            <!--end foter-->

            <footer>
                <div class="row">
                    <div class="col-md-4 col-12">
                        <h5>All rights reserved for crazy idea 2020 ©</h5>
                    </div>

                    <div class="col-md-4 col-12">

                        <div class="soc">
                            <div class="row">
                                <span class="col text-center"><a href="#" class="social1 text-center"><i
                                            class="fab fa-facebook-f"></i></a></span>
                                <span class="col text-center"><a href="#" class="social2 text-center"><i
                                            class="fab fa-instagram"></i></a></span>
                                <span class="col text-center"><a href="#" class="social3 text-center"><i
                                            class="fab fa-youtube"></i></a></span>
                                <span class="col text-center"><a href="#" class="social4 text-center"><i
                                            class="fab fa-behance"></i></a></span>

                            </div>



                        </div>


                    </div>

                    <div class="col-md-3 col-12">

                        <div class="crazy">
                            <h6>Made with <img src="images/red.svg"> by Crazy Idea</h6>
                            <p class="text-right">Think Out Of The Box</p>
                        </div>

                    </div>
                </div>
            </footer>
        </div>
    </div>
    <!--end main footer-->
</template>

<script>
export default {

}
</script>

<style>
/*start main-footer*/
.main-footer {
    background-image: url('/footer.svg');
    background-repeat: no-repeat;
    background-size: cover;
    padding-top: 20%;


}

.main-footer .on-touch {
    padding-top: 15px;
    border-bottom: .5px dotted #fff;
    padding-bottom: 50px;
}

.main-footer .on-touch p {
    font-family: made-bold;
    font-size: 39px;
    color: #ffffff;

}

.main-footer .on-touch input {
    width: 80%;
    background-color: #ffffff;
    border: 1px solid transparent;
    border-radius: 7px;
    height: 42px;
    margin-top: 4px;

}

.main-footer .on-touch input::placeholder {
    font-style: italic;
    padding-left: 5px;
}

.main-footer .on-touch a {
    display: inline-block;
    width: 30px;
    height: 30px;
    background-color: #428EF3;
    color: #ffffff;
    border-radius: 5px;
    position: absolute;
    left: 68%;
    margin-top: 10px;
    padding-top: 2px;

}

.main-footer .foter {
    margin-top: 100px;
    border-bottom: .5px dotted #fff;
    padding-bottom: 50px;

}

.main-footer .foter img {
    width: 60%;
    height: 120px;
}

.main-footer .foter ul {
    padding-left: 0px;
}

.main-footer .foter h4 {
    color: #ffffff;
    font-family: semi;
    font-size: 26px;
    margin-bottom: 21px;
}

.main-footer .foter ul li,
.main-footer .foter ul li a {
    margin-top: 10px;
    margin-bottom: 10px;
    color: #ffffff;
    font-family: pop-reg;
    font-size: 18px;
    margin-left: 3px;
}

.main-footer .foter p {
    display: inline-block;
    font-family: pop-reg;
    color: #ffffff !important;
    font-size: 18px;
    margin-top: 10px;
    margin-bottom: 10px;
}

.main-footer .foter span {
    color: #00FFEE;
    font-size: 19px;
    margin-top: 2px;
}

.foter .det h4 {
    margin-left: 22px;
}

footer {
    padding-top: 22px;
    padding-bottom: 22px;
}

footer h5 {
    color: #ffffff;
    font-family: med;
    font-size: 16px;
    margin-top: 15px;
}

.soc {
    margin-top: 15px;
}

footer .social {
    display: inline-block;
    width: 33px;
    height: 33px;
    color: #00153F;
    border: 1px solid #ffffff;
    border-radius: 50%;
    font-size: 18px;
    margin-right: 5px;
    margin-left: 5px;
    background-color: #ffffff;
    transition: all .3s ease-in-out;
}
footer .social:hover {
    color: #00ffee;
}

footer .crazy h6 {
    font-family: pop-reg;
    color: #ffffff;
    margin-right: -30%;
    text-align: right;
    font-size: 18px;
}


footer .crazy p {
    color: #ffffff;
    margin-right: -15%;
    font-family: pop-reg;
}

/*end main-footer*/
</style>