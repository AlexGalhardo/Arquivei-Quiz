<template>
    <div class="panel panel-default" id="container-questions">
        <div class="panel-heading">
            <h3 class="panel-title text-center">{{ question }}</h3>
        </div>
        <div class="panel-body">
            <div class="col-xs-12 col-sm-6 text-center">
                <button class="btn btn-primary btn-lg" style="margin: 10px" @click="onAnswer(btnData[0].correct)">{{ btnData[0].answer }}</button>
            </div>
            <div class="col-xs-12 col-sm-6 text-center">
                <button class="btn btn-primary btn-lg" style="margin: 10px" @click="onAnswer(btnData[1].correct)">{{ btnData[1].answer }}</button>
            </div>
            <div class="col-xs-12 col-sm-6 text-center">
                <button class="btn btn-primary btn-lg" style="margin: 10px" @click="onAnswer(btnData[2].correct)">{{ btnData[2].answer }}</button>
            </div>
            <div class="col-xs-12 col-sm-6 text-center">
                <button class="btn btn-primary btn-lg" style="margin: 10px" @click="onAnswer(btnData[3].correct)">{{ btnData[3].answer }}</button>
            </div>
        </div>
    </div>
</template>


<style>
    #container-questions {
        box-shadow: 10px 10px rgba(0, 0, 0, 0.3);
    }

    .btn:hover {
        box-shadow: 5px 5px gray;
    }

</style>


<script>
    
    export default{
        data() {
            return {
                question: 'Oops, an error ocurred :/',
                btnData: [
                    {correct: true, answer: 0},
                    {correct: false, answer: 0},
                    {correct: false, answer: 0},
                    {correct: false, answer: 0}
                ]
            };
        },
        methods: {
            generateQuestion() {

                const respostas1 = ['+ de 100 mil clientes', '+ de 30 mil clientes', '+ de 50 mil clientes', '+ de 70 mil clientes'];
                const respostas2 = ['XML', 'NFe', 'CTe', 'NFee'];
                const respostas3 = ['McDonalds', 'Xiomi', 'EPSON', 'KraftHeinz'];
                const respostas4 = ['R$29,90', 'R$49,90', 'R$89,90', 'R$69,90'];
                const respostas5 = ['Alex Galhardo :D', 'Darth Vader', 'Tyrion Lannister', 'Marvin the Paranoid'];
                const respostas6 = ['PlayStation 5', 'Coffe', 'Paçoquinha', 'Xbox Two'];
                const respostas7 = ['Simpsons', 'Westworld', 'Rick and Martin', 'Game of Thrones'];
                const respostas8 = ['Chá', 'Coca-Cola', 'MUITO Coffe', 'Pipoca'];
                const respostas9 = ['Banco Central', 'Ministério da Fazenda', 'Sefaz', 'Camâra Municipal'];

                let modeNumber = this.generateRandomNumber(1, 9);

                

                switch (modeNumber) {

                    case 1:

                        //correctAnswer = respostas1[2];
                        this.question = `Quantos clientes a empresa possui atualmente?`;
                        // Já deve ter passado, mas a referência está no site :b
                        
                        this.btnData[0].answer = respostas1[0];
                        this.btnData[0].correct = false;

                        this.btnData[1].answer = respostas1[1];
                        this.btnData[1].correct = false;

                        this.btnData[2].answer = respostas1[2];
                        this.btnData[2].correct = true;

                        this.btnData[3].answer = respostas1[3];
                        this.btnData[3].correct = false;

                        break;


                    case 2:

                        //correctAnswer = respostas2[3];
                        this.question = `Qual destas NÃO é nota fiscal?`;
                        // Será que não existe Nfee? Estou com medo
                        
                        this.btnData[0].answer = respostas2[0];
                        this.btnData[0].correct = false;

                        this.btnData[1].answer = respostas2[1];
                        this.btnData[1].correct = false;

                        this.btnData[2].answer = respostas2[2];
                        this.btnData[2].correct = false;

                        this.btnData[3].answer = respostas2[3];
                        this.btnData[3].correct = true;

                        break;

                    case 3:

                        //correctAnswer = respostas3[1];
                        this.question = `Qual destas empresas NÃO é cliente da Arquivei ainda? (Eu acho)`;
                        // logo mais será 
                        
                        this.btnData[0].answer = respostas3[0];
                        this.btnData[0].correct = false;

                        this.btnData[1].answer = respostas3[1];
                        this.btnData[1].correct = true;

                        this.btnData[2].answer = respostas3[2];
                        this.btnData[2].correct = false;

                        this.btnData[3].answer = respostas3[3];
                        this.btnData[3].correct = false;

                        break;

                    case 4:

                        //correctAnswer = respostas4[3];
                        this.question = `Qual destes planos não esta incluido na Arquivei?`;
                        // 69,90
                        
                        this.btnData[0].answer = respostas4[0];
                        this.btnData[0].correct = false;

                        this.btnData[1].answer = respostas4[1];
                        this.btnData[1].correct = false;

                        this.btnData[2].answer = respostas4[2];
                        this.btnData[2].correct = false;

                        this.btnData[3].answer = respostas4[3];
                        this.btnData[3].correct = true;

                        break;

                    case 5:

                        //correctAnswer = respostas5[0];
                        this.question = `Qual destes é o novo estagiário da Arquivei?`;
                        // this is mee :p
                        
                        this.btnData[0].answer = respostas5[0];
                        this.btnData[0].correct = true;

                        this.btnData[1].answer = respostas5[1];
                        this.btnData[1].correct = false;

                        this.btnData[2].answer = respostas5[2];
                        this.btnData[2].correct = false;

                        this.btnData[3].answer = respostas5[3];
                        this.btnData[3].correct = false;

                        break;

                    case 6:

                        this.question = `O que é que mais tem dentro da Arquivei?`;
                        // coffe :D
                        
                        this.btnData[0].answer = respostas6[0];
                        this.btnData[0].correct = false;

                        this.btnData[1].answer = respostas6[1];
                        this.btnData[1].correct = true;

                        this.btnData[2].answer = respostas6[2];
                        this.btnData[2].correct = false;

                        this.btnData[3].answer = respostas6[3];
                        this.btnData[3].correct = false;

                        break;

                    case 7:

                        this.question = `Qual a série preferida da galera da Arquivei?`;
                        // got, é claro :D
                        
                        this.btnData[0].answer = respostas7[0];
                        this.btnData[0].correct = false;

                        this.btnData[1].answer = respostas7[1];
                        this.btnData[1].correct = false;

                        this.btnData[2].answer = respostas7[2];
                        this.btnData[2].correct = false;

                        this.btnData[3].answer = respostas7[3];
                        this.btnData[3].correct = true;

                        break;

                    case 8:

                        this.question = `O que não pode faltar na Arquivei de jeito nenhum?`;
                        // eu acho que é coffe hein :D
                        
                        this.btnData[0].answer = respostas8[0];
                        this.btnData[0].correct = false;

                        this.btnData[1].answer = respostas8[1];
                        this.btnData[1].correct = false;

                        this.btnData[2].answer = respostas8[2];
                        this.btnData[2].correct = true;

                        this.btnData[3].answer = respostas8[3];
                        this.btnData[3].correct = false;

                        break;

                    case 9:

                        this.question = `De onde saem as notas fiscais, para serem armazenadas na Arquivei?`;
                        // sefaz
                        
                        this.btnData[0].answer = respostas9[0];
                        this.btnData[0].correct = false;

                        this.btnData[1].answer = respostas9[1];
                        this.btnData[1].correct = false;

                        this.btnData[2].answer = respostas9[2];
                        this.btnData[2].correct = true;

                        this.btnData[3].answer = respostas9[3];
                        this.btnData[3].correct = false;

                        break;


                    default:
                        correctAnswer = 0;
                        this.question = 'Um bug apareceu!';
                }

            },
            generateRandomNumber(min, max, except) {
                
                const rndNumber = Math.round(Math.random() * (max - min)) + min;
                console.log(min, max, rndNumber);
                if (rndNumber == except) {
                    return this.generateRandomNumber(min, max, except);
                }
                return rndNumber;
            },
            onAnswer(isCorrect) {
                this.$emit('answered', isCorrect);
            }
        },
        created() {
            this.generateQuestion();
        }
    }
</script>
