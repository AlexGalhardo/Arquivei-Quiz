// Componente principal da aplicação

<template>
    <div class="container">

        <!-- Header -->
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1 class="text-center" id="title-quiz">Arquivei Quiz</h1>
            </div>
        </div>

        <hr>

        <!-- Container das Perguntas -->
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <transition name="flip" mode="out-in">
                    <component :is="mode" @answered="answered($event)" @confirmed="mode = 'app-question'"></component>
                </transition>
            </div>
        </div>

        <hr>

        <!-- Footer -->
         <div class="row"> 
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <p class="text-center"> Made with <span style="color: red;">&hearts;</span> in São Carlos</p>
                 <p class="text-center"> &copy; Alex Galhardo</p><br><br>
                 <p class="text-center"> Project made to maybe be the next intern at Arquivei <span style="color: red;">&hearts;</span> </p>
            </div>
        </div>


    </div>
</template>

<script>
    import Question from './components/Question.vue';
    import Answer from './components/Answer.vue';

    export default {
        data() {
            return {
                mode: 'app-question'
            }
        },
        methods: {
          answered(isCorrect) {
              if (isCorrect) {
                  this.mode = 'app-answer';
              } else {
                  this.mode = 'app-question';
                  alert("Hey Luke, I'm your Daddy...Ops, sorry. Wrong Answer.");
              }
          },
        },
        components: {
            appQuestion: Question,
            appAnswer: Answer
        }
    }
</script>

<style>
    .flip-enter {
        /*transform: rotateY(0deg);*/
    }

    .flip-enter-active {
        animation: flip-in  0.5s ease-out forwards;
    }

    .flip-leave {
        /*transform: rotateY(0deg);*/
    }

    .flip-leave-active {
        animation: flip-out 0.5s ease-out forwards;
    }

    @keyframes flip-out {
        from {
            transform: rotateY(0deg);
        }
        to {
            transform: rotateY(90deg);
        }
    }

    @keyframes flip-in {
        from {
            transform: rotateY(90deg);
        }
        to {
            transform: rotateY(0deg);
        }
    }

    body {
        background-color: #eeeeee;
    }

    h1 {
        color: blue;
    }

    .container-questions {
        box-shadow: 5px 5px gray;
    }

    #title-quiz:hover {
        text-shadow: 10px 10px rgba(0, 0, 0, 0.2);
    }

</style>
