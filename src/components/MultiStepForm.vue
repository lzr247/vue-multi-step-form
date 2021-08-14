<template>
    <div class="container">
        <article>
            <header>
                <div class="progress">
                    <div class="progress-step"
                        :class="{ 'active':index === activeStep }"
                        v-for="(step, index) in formSteps"
                        :key="'step' + index"
                    >
                        {{ index + 1 }}
                    </div>
                </div>
            </header>
            <section>

            </section>
        </article>
    </div>
</template>
<script>
export default {
    data: () => {
        return {
            activeStep: 0,
            formSteps: [
                {
                    title: 'HTML Quiz',
                    fields: [
                        { label: 'What does HTML stands for?', value: '', valid: true, pattern: /.+/ },
                        { label: 'Who is making the Web standards?', value: '', valid: true, pattern: /.+/ },
                        { label: 'Element for the largest heading?', value: '', valid: true, pattern: /.+/ }
                    ]
                },
                {
                    title: 'CSS Quiz',
                    fields: [
                        { label: 'What does CSS stands for?', value: '', valid: true, pattern: /.+/  },
                        { label: 'HTML tag for an internal style sheet?', value: '', valid: true, pattern: /.+/ },
                        { label: 'Property for the background color?', value: '', valid: true, pattern: /.+/ }
                    ]
                },
                {
                    title: 'Your data',
                    fields: [
                        { label: 'Your first name?', value: '', valid: true, pattern: /.+/  },
                        { label: 'Your last name?', value: '', valid: true, pattern: /.+/ },
                        { label: 'Your email?', value: '', valid: true, pattern: /^[^\s@]+@[^\s@]+\.[^\s@]+$/ }
                    ]
                },
                {
                    title: 'Thank you for participating!'
                }
            ]
        }
    }
}
</script>
<style lang="scss" scoped>
    @import url('https://fonts.googleapis.com/css?family=Noto+Sans&display=swap');

    @mixin flexbox() {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .container {
        @include flexbox();
        width: 100%;
        min-height: 100vh;
        font-family: 'Noto Sans', sans-serif;
        background: radial-gradient(#DF5C2E, #A43227);
    }

    article {
        display: flex;
        margin: 10px;
        width: calc(100% - 20px);
        max-width: 720px;
        min-height: 480px;

        header {
            @include flexbox();
            width: 60px;
            height: 480px;
            background-color: #fff;
            border-right: 2px dotted #df5c2e;
            box-shadow: 0 15px 30px rgba(0, 0, 0, .2),
                        0 10px 10px rgba(0, 0, 0, .2);
        }

        .progress-step {
            @include flexbox();
            position: relative;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            margin-bottom: 20px;
            color: #fff;    
            background-color: #DF5C2E;
            font-weight: bold;

            &.active {
                background-color: #DF5C2E;
            }
        }
    }

</style>