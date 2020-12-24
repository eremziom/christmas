<template>
    <div id="background" class="background d-flex flex-column justify-content-between">
        <div v-if="firstPart">
            <div class="d-flex container">
                <div v-if="welcomeText" id="welcome" class="typewriter">
                    <h1>{{welcome}}</h1>
                </div>
                <div v-if="firstQuestion" id="firstQuestion" class="typewriter2">
                    <h3>{{firstQuestionText}}</h3>
                </div>
                <div v-if="secQuestion" id="secQuestion" class="typewriter3">
                    <h3>{{secQuestionText}}</h3>
                </div>
                <div v-if="thirdQuestion" id="thirdQuestion" class="typewriter4">
                    <h3>{{thirdQuestionText}}</h3>
                </div>
                <div v-if="gratz" id="gratz" class="typewriter5">
                    <h3>{{gratzText}}</h3>
                </div>
            </div>
            <div v-if="fbuttons" id="fbuttons" class="d-flex justify-content-around container buttons-fade">
                <button type="button" class="btn btn-dark wide" v-on:click="fyes">Tak</button>
                <button type="button" class="btn btn-dark wide" v-on:click="fno">Nie</button>
            </div>
            <div v-if="sbuttons" id="s-buttons" class="d-flex justify-content-around container buttons-fade">
                <button type="button" class="btn btn-dark wide" v-on:click="syes">Tak</button>
                <button type="button" class="btn btn-dark wide" v-on:click="sno">Nie</button>
            </div>
            <div v-if="tbuttons" id="t-buttons" class="d-flex justify-content-around container buttons-fade">
                <button type="button" class="btn btn-dark wide" v-on:click="tyes">Tak</button>
                <button type="button" class="btn btn-dark wide" v-on:click="tno">Nie</button>
            </div>
            <div v-if="lbuttons" id="l-buttons" class="d-flex justify-content-around container buttons-fade">
                <button type="button" class="btn btn-dark" v-on:click="showOptions">POKAŻ PREZENTY</button>
            </div>
            <div v-if="mbuttons" id="m-buttons" class="d-flex justify-content-around container buttons-fade">
                <button type="button" id="butdis" class="btn btn-dark" v-on:click="mixGifts">WYLOSUJ PREZENT</button>
            </div>
        </div>
        <div v-if="giftsShow" id="gifts-container" class="giftsContainer d-flex justify-content-center">   
            <div class="card" id="barbie" style="width: 200px;">
                <img class="card-img-top hgt" v-bind:src="require('../assets/barbie.jpg')" alt="Card image cap">
                <div class="card-body">
                    <p class="card-text">Lalka Barbie, czarodziejka i ksieżniczka w jednym! Różowa, idealna dla dziewczynki</p>
                </div>
            </div>
            <div class="card" id="cities" style="width: 200px;">
                <img class="card-img-top hgt" v-bind:src="require('../assets/cities.jpg')" alt="Card image cap">
                <div class="card-body">
                    <p class="card-text">Gra Cites: Skylines, zostań największym projektantem i budowniczym Wirtualnego Miasta!</p>
                </div>
            </div>
            <div class="card" id="shovel" style="width: 200px;">
                <img class="card-img-top hgt" v-bind:src="require('../assets/shovel.jpg')" alt="Card image cap">
                <div class="card-body">
                    <p class="card-text">Łopata, idealna do odśnieżania podjazdu do garażu i ogródka. Pomarańczowa z drewnianą rączką</p>
                </div>
            </div>

        </div>
        <div v-if="starsHide" class="d-flex justify-content-center lower">
            <div v-if="counter > 0" id="star1" class="img-container">
                <img v-bind:src="require('../assets/star.png')" class="img-fluid" alt="Responsive image">
            </div>
            <div v-if="counter > 1" id="star2" class="img-container">
                <img v-bind:src="require('../assets/star.png')" class="img-fluid" alt="Responsive image">
            </div>
            <div v-if="counter > 2" id="star3" class="img-container">
                <img v-bind:src="require('../assets/star.png')" class="img-fluid" alt="Responsive image">
            </div>
        </div>
        <div v-if="secondPart" class="containerGame d-flex flex-column justify-content-between">
            <div class="texts d-flex flex-column align-items-center">
                <h1>Drogi Darku,</h1>
                <h2>W Wigilię Bożego Narodzenia
                    <br>
                Święty Mikołaj chciałby złożyć Ci najserdeczniejsze życzenia,
                <br>
                a ponieważ byłeś grzeczny, słuchałeś rodziców i opiekowałeś się
                <br>
                swoim młdoszym bratem Adriankiem,
                z przyjemnością wręcza Ci prezent, którym jest gra:</h2>
            </div>
            <div class="instructions d-flex justify-content-center">
                <button type="button" id="butdis" class="btn btn-warning" v-on:click="goInst">Kliknij tutaj żeby przeczytać instrukjce instalacji</button>
            </div>
            <div v-if="instruct" class="inst-container">
            </div>
            <div v-if="instruct" class="inst-info d-flex flex-column align-items-center justify-content-between">
                <div class="instructDiv">
                    <p>1. Kliknij w <a target="_blank" href="https://www.epicgames.com/store/pl/">link</a>, żeby pobrać platformę Epic Games Store</p>
                    <p>2. W nowej zakładce, w prawym górnym rogu, kliknij w niebieski przycisk <i>Pobierz Epic Games</i>. Platforma pobierze się automatycznie</p>
                    <p>3. Po zakończeniu pobierania, uruchom plik <i>EpicInstaller</i> (znajdziesz go albo w lewym dolnym rogu przeglądarki internetowej, albo w folderze Pobrane na Twoim komputerze)</p>
                    <p>4. Zainstaluj platformę Epic Games (postępuj zgodnie z instrukcjami instalatora, zaczekaj też na pobranie aktualizacji)</p>
                    <p>5. Wybierz sposób logowania: "Zaloguj się poprzez Epic Games" (pierwsza opcja na samej górze)</p>
                    <p>6. Użyj adresu mailowego swojego taty i hasła <strong>Darek123Kryczka</strong></p>
                    <p>7. Po zalogowaniu do platformy, w menu z lewej strony kliknij przycisk <i>Biblioteka</i></p>
                    <p>8. Zainstaluj grę <b>Cities: Skylines</b>, lub jedną z trzech pozostałych gier, które również dostałeś w prezencie od Świętego Mikołaja :)</p>
                    <p style="text-align: center"> WESOŁYCH ŚWIĄT!!</p>
                </div>
                <div class="instructions d-flex justify-content-center">
                    <button type="button" id="butclose" class="btn btn-warning" v-on:click="closeInst">Zamknij instrukcję</button>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    name: 'Main',
        async mounted(){
            await this.showBackground()
            document.getElementById('background').classList.add('background-img')
            await this.sleepFunc()
            await this.firstQ()
            await this.question()
        },
    methods: {
        fyes(){
            this.counter++;
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.firstYesFunc());
                }, 100);
            })
        },
        fno(){
            console.log('no');
        },
        firstYesFunc(){
            this.firstYes = true
            this.fbuttons = false;
            document.getElementById('firstQuestion').classList.add('fade');
            document.getElementById('star1').classList.add('img-container-grow');
            
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.endFirstQ());
                }, 3000);
            })
        },
        endFirstQ(){
            this.firstQuestion = false;
            this.secQuestion = true;
            this.sbuttons = true;
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(document.getElementById('s-buttons').classList.add('fadeIn'));
                }, 500);
            })
        },
        syes(){
            this.counter++;
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.secYesFunc());
                }, 100);
            })
        },
        secYesFunc(){
            this.secYes = true
            this.sbuttons = false;
            document.getElementById('secQuestion').classList.add('fade');
            document.getElementById('star2').classList.add('img-container-grow');
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.endSecQ());
                }, 3000);
            })
        },
        endSecQ(){
            this.secQuestion = false;
            this.thirdQuestion = true;
            this.tbuttons = true;
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(document.getElementById('t-buttons').classList.add('fadeIn'));
                }, 500);
            })
        },
        sno(){
            console.log('no')
        },
        tyes(){
            this.counter++;
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.thirdYesFunc());
                }, 100);
            })
        },
        thirdYesFunc(){
            // this.thirdYes = true
            this.tbuttons = false;
            document.getElementById('thirdQuestion').classList.add('fade');
            document.getElementById('star3').classList.add('img-container-grow');
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.endThirdQ());
                }, 3000);
            })
        },
        endThirdQ(){
            this.thirdQuestion = false;
            this.gratz = true;
            this.lbuttons = true;
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(document.getElementById('l-buttons').classList.add('fadeIn'));
                }, 500);
            })
        },
        tno(){
            console.log('no')
        },
        sleepFunc() {
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.test());
                }, 3000);
            });
        },
        test(){
            console.log('test');
            this.welcomeText = true;
        },
        showBackground() {
            return new Promise(resolve => {
                setTimeout(() => {
                resolve();
                }, 1000);
            });
        },
        firstQ(){
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.clear());
                }, 3000);
            });
        },
        async clear(){
            document.getElementById('welcome').classList.add('fade');
        },
        question(){
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.newText());
                }, 3000);
            });
        },
        async newText(){
            this.welcomeText = false;
            this.firstQuestion = true;
            await this.firstButtons();
        },
        firstButtons(){
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.newButtons());
                }, 3000);
            });
        },
        newButtons(){
            this.fbuttons = true;
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(document.getElementById('fbuttons').classList.add('fadeIn'));
                }, 500);
            });
        },
        showOptions(){
            this.giftsShow = true;
            this.starsHide = false;
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.showImages());
                }, 500);
            });
        },
        showImages(){
            document.getElementById('gifts-container').classList.remove('giftsContainer');
            document.getElementById('gifts-container').classList.add('fadeInImages');
            this.starsHide = false;
            this.lbuttons = false;
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.endGifts());
                }, 1000);
            });

        },
        endGifts(){
            this.mbuttons = true;
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(document.getElementById('m-buttons').classList.add('fadeIn'));
                }, 500);
            })
        },
        async mixGifts(){
            document.getElementById('butdis').disabled = true;
            console.log('clik?')
            for(let x = 1; x<15; x++){
                await this.lightBarbie();
                await this.lightCities();
                await this.lightShovel();
            }
            await this.lightBarbie();
            await this.lightCities();
            for(let x = 1; x<5; x++){
                await this.lightCitiesBlinkOn();
                await this.lightCitiesBlinkOff();
            }
            await this.wait();
            
        },
        lightBarbie(){
            console.log('barbie')
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(document.getElementById('barbie').classList.add('border'));
                resolve(document.getElementById('cities').classList.remove('border'));
                resolve(document.getElementById('shovel').classList.remove('border'));
                }, 100);
            })
        },
        lightCities(){
            console.log('cities')
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(document.getElementById('cities').classList.add('border'));
                resolve(document.getElementById('barbie').classList.remove('border'));
                resolve(document.getElementById('shovel').classList.remove('border'));
                }, 100);
            })
        },
        lightShovel(){
            console.log('shovel')
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(document.getElementById('shovel').classList.add('border'));
                resolve(document.getElementById('barbie').classList.remove('border'));
                resolve(document.getElementById('cities').classList.remove('border'));
                }, 100);
            })
        },
        lightCitiesBlinkOn(){
            console.log('cities')
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(document.getElementById('cities').classList.remove('border'));
                }, 100);
            })
        },
        lightCitiesBlinkOff(){
            console.log('cities')
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(document.getElementById('cities').classList.add('border'));
                }, 100);
            })
        },
        wait(){
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.shutAll());
                }, 2000);
            })
        },
        shutAll(){
            this.gratz = false;
            this.mbuttons = false;
            this.giftsShow = false;
            this.firstPart = false;
            document.getElementById('background').classList.remove('background');
            document.getElementById('background').classList.remove('background-img');
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(this.newBackground());
                }, 500);
            })
        },
        newBackground(){
            document.getElementById('background').classList.add('background2');
            this.secondPart = true;
            return new Promise(resolve => {
                setTimeout(() => {
                resolve(document.getElementById('background').classList.add('fadeIn'));
                }, 500);
            })
        },
        goInst(){
            console.log('instrukcje')
            this.instruct = true;
        },
        closeInst(){
           this.instruct = false; 
        }

    },
    data(){
        return{
            welcome: 'WITAJ DAREK',
            firstQuestionText: 'Czy byłeś w tym roku grzeczny?',
            welcomeText: false,
            background: false,
            firstQuestion: false,
            fbuttons: false,
            firstYes: false,
            secYes: false,
            secQuestionText: 'A czy słuchałeś swoich rodziców?',
            secQuestion: false,
            sbuttons: false,
            thirdQuestion: false,
            tbuttons: false,
            thirdQuestionText: 'Czy opiekowałeś się swoim braciszkiem?',
            counter: 0,
            gratzText: 'W takim razie zasłużyłeś na prezent!',
            gratz: false,
            lbuttons: false,
            giftsShow: false,
            starsHide: true,
            mbuttons: false,
            firstPart: true,
            secondPart: false,
            testus: false,
            instruct: false,
        }
    }
}
</script>
<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Langar&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Russo+One&display=swap');
.background {
  background-image: url('../assets/moon.jpg');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
  background-color: black;
  -webkit-transition: opacity 3s ease-in-out;
  -moz-transition: opacity 3s ease-in-out;
  -o-transition: opacity 3s ease-in-out;
  transition: opacity 3s ease-in-out;
  opacity: 0;
}
.background2 {
  background-image: url('../assets/cities2.jpg');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
  background-color: white;
  opacity: 0;
}
.background-img {
    opacity: 1;
}
.buttons-fade {
    font-family: 'Langar', cursive;
    opacity: 0;
}
.container{
    padding-top: 50px;
    width: 600px;
}
.lower{
    padding-bottom: 50px;
}
.img-container {
    width: 0px;
    padding: 20px;
}
.img-container-grow {
    width:150px;
    -webkit-transition: 1s ease-in-out;
    -moz-transition: 1s ease-in-out;
    -o-transition: 1s ease-in-out;
    transition: 1s ease-in-out;
}
.typewriter h1{
    font-family: 'Langar', cursive;
    overflow: hidden; /* Ensures the content is not revealed until the animation */
    border-right: .15em solid transparent; /* The typwriter cursor */
    white-space: nowrap; /* Keeps the content on a single line */
    //   margin: 0 auto; /* Gives that scrolling effect as the typing happens */
    letter-spacing: .15em; /* Adjust as needed */
    animation: 
        typing 1s steps(11, end),
        blink-caret 0.6s step-end infinite;
}
.typewriter2 h3{
    font-family: 'Langar', cursive;
    overflow: hidden; /* Ensures the content is not revealed until the animation */
    border-right: .15em solid transparent; /* The typwriter cursor */
    opacity: 1;
    white-space: nowrap; /* Keeps the content on a single line */
    //   margin: 0 auto; /* Gives that scrolling effect as the typing happens */
        // width: 530px;
    letter-spacing: .15em; /* Adjust as needed */
    animation: 
        typing 2s steps(30, end),
        blink-caret 0.6s step-end infinite;
    
}
.typewriter3 h3{
    font-family: 'Langar', cursive;
    overflow: hidden; /* Ensures the content is not revealed until the animation */
    border-right: .15em solid transparent; /* The typwriter cursor */
    opacity: 1;
    white-space: nowrap; /* Keeps the content on a single line */
    letter-spacing: .15em; /* Adjust as needed */
    animation: 
        typing 2s steps(30, end),
        blink-caret 0.6s step-end infinite;
}
.typewriter4 h3{
    font-family: 'Langar', cursive;
    overflow: hidden; /* Ensures the content is not revealed until the animation */
    border-right: .15em solid transparent; /* The typwriter cursor */
    opacity: 1;
    white-space: nowrap; /* Keeps the content on a single line */
    letter-spacing: .15em; /* Adjust as needed */
    animation: 
        typing 2s steps(30, end),
        blink-caret 0.6s step-end infinite;
}
.typewriter5 h3{
    font-family: 'Langar', cursive;
    overflow: hidden; /* Ensures the content is not revealed until the animation */
    border-right: .15em solid transparent; /* The typwriter cursor */
    opacity: 1;
    white-space: nowrap; /* Keeps the content on a single line */
    letter-spacing: .15em; /* Adjust as needed */
    animation: 
        typing 2s steps(40, end),
        blink-caret 0.6s step-end infinite;
}
.typewriter6 h2{
    font-family: 'Langar', cursive;
    overflow: hidden; /* Ensures the content is not revealed until the animation */
    border-right: .15em solid transparent; /* The typwriter cursor */
    opacity: 1;
    white-space: nowrap; /* Keeps the content on a single line */
    letter-spacing: .15em; /* Adjust as needed */
    animation: 
        typing 2s steps(40, end),
        blink-caret 0.6s step-end infinite;
}
.fade{
    opacity: 0;
    -webkit-transition: opacity 3s ease-in-out;
    -moz-transition: opacity 3s ease-in-out;
    -o-transition: opacity 3s ease-in-out;
    transition: opacity 3s ease-in-out;
}
.fadeIn{
    opacity: 0.8;
    -webkit-transition: opacity 2s ease-in-out;
    -moz-transition: opacity 2s ease-in-out;
    -o-transition: opacity 2s ease-in-out;
    transition: opacity 2s ease-in-out;
}
.fadeInImages{
    opacity: 1;
    -webkit-transition: opacity 2s ease-in-out;
    -moz-transition: opacity 2s ease-in-out;
    -o-transition: opacity 2s ease-in-out;
    transition: opacity 2s ease-in-out;
    padding-bottom: 20px;
}
.giftsContainer {
    opacity: 0;
}

/* The typing effect */
@keyframes typing {
  from { width: 0 }
  to { width: 100% }
}

/* The typewriter cursor effect */
@keyframes blink-caret {
  from, to { border-color: transparent }
  50% { border-color: #2c3e50; }
}
.wide {
    width: 100px;
}
.btn {
    font-size: 20px;
}
.hgt {
    height: 300px;
}
.card {
    margin: 0 20px;
}
.border {
background-color: rgb(61, 44, 11);
color: white;
}
.containerGame {
    width: 1000px;
    margin: 0 auto;
    padding-top: 50px;
    height: 100vh;
}
.texts {
    font-family: 'Langar', cursive;
    color: #00456e;
    text-align: center;
    background-color: #fff;
    background-color: rgba(255, 255, 255, 0.5);

}
.instructions {
    font-family: 'Langar', cursive;
    color: rgb(30, 30, 46);
    text-align: center;
    padding-bottom: 50px;
}
.inst-container {
    position: absolute;
    width: 100%;
    height: 100%;
        background-color: #fff;
    background-color: rgba(255, 255, 255, 0.5);
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.inst-info {
    position: absolute;
    width: 500px;
    height: 100%;
    background-color: #fff;
    background-color: rgba(255, 255, 255, 0.9);
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 10;
}
.instructDiv{
    padding-top: 20px;
    padding-left: 20px;
}
</style>