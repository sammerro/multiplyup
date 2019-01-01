<template>
    <div class="question-container">
        <p>
            How much is...
        </p>
        <h2 class="equation">
             {{question}}
        </h2>
        <div class="answers">
            <div class="answer" v-for="(answer, index) in answers" @click="answerChosen(answer.ifCorrect, index)" :key="index" :class="{darken: selected === index} ">
                <p>
                    {{answer.content}} 
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {

    data() {
        return {
            question: 'Something went wrong',
            answers: [
                {ifCorrect: true, content: 0},
                {ifCorrect: true, content: 0},
                {ifCorrect: true, content: 0},
                {ifCorrect: true, content: 0}
            ],
            selected: undefined
        }
    },

    methods: {
        createNewQuestion() { 
            //numbers from 1 to 10
            const a = this.generateRandomNumber(5.5,3.5,false);
            const b = this.generateRandomNumber(5.5,3.5,false);
            const result = a*b;
            this.question = `${a} \xD7 ${b}`
            //position of correct answer
            const correctIndex = Math.floor(Math.random()*4);

            // using set characteristic to not repeat values
            const setAnswers = new Set();
            while (setAnswers.size < 4) {
                setAnswers.add(this.generateRandomNumber(result, 10));
            }
            const arrAnswers = [...setAnswers];
            this.answers[0].ifCorrect = false;
            this.answers[1].ifCorrect = false;
            this.answers[2].ifCorrect = false;
            this.answers[3].ifCorrect = false;

            this.answers[0].content = arrAnswers[0];       
            this.answers[1].content = arrAnswers[1];       
            this.answers[2].content = arrAnswers[2];       
            this.answers[3].content = arrAnswers[3];    
            
            this.answers[correctIndex].ifCorrect = true;
            this.answers[correctIndex].content = result;

        },
        generateRandomNumber(center, radius, excludeCenter=true) {
            let rand;
            do {
                rand = Math.round(center + (Math.random() - 0.5) * 2 * radius);
            } while (rand === center && excludeCenter);
            return rand;
        },
        answerChosen(ifCorrect, id) {
            this.selected = id;
            this.$emit('answerChosen',ifCorrect);
        }
    },

    created() {
        this.createNewQuestion();
    },
}
</script>

<style lang="scss" scoped>
    .question-container {
        height: 100%;
        width: 100%;
        display: flex;
        flex-flow: column nowrap;
        align-items: center;
        justify-content: center;
        .equation {
            font-size: 2.3em;
            padding: .2em .5em .5em;
            font-weight: 300;

        }
        @media (orientation: portrait), (min-width: 700px) {
            .equation {
                padding: .5em 1em 1em  1em;
            }
        }
        .answers {
            display: grid;
            grid-template-columns: 1fr 1fr;
            justify-items: center;
            align-items: center;
            grid-gap: 5vmin;
            .answer {
                background-color: var(--third-color);
                cursor: pointer;
                font-size: 1.5em;
                width: 4em;
                height: 4em;
                line-height: 4em;
                text-align: center;
                border: 1.5px solid var(--text-color-main);
                border-radius: 50%;
                transition: all .15s;
            }
        }
        @media (orientation: landscape) {
            .answers {
                grid-template-columns: 1fr 1fr 1fr 1fr;
                grid-gap: 1em;
                .answer {

                }
            }
        }

    }
</style>

