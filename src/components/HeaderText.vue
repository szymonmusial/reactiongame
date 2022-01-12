<template>
<h1>{{displayedTitle}}</h1>
</template>

<script>
export default {
    name: 'HeaderText',
    props: ['reactionTime'],
    computed: {
        displayedTitle() {
            let roundedReactionTime = Math.floor(this.reactionTime() / 100)
            let title = "Reaction test game"
            if (roundedReactionTime > 0) {
                switch (roundedReactionTime) {
                    case 0:
                        title = "swietnie!"
                        break;
                    case 1:
                        title = " Chyba oszukiwałeś "
                        break;
                    case 2:
                        title = " Ale jesteś szybki "
                        break;
                    case 3:
                        title = " Wow Wow "
                        break;
                    case 4:
                        title = " teraz to mi zaimponowałeś "
                        break;
                    case 5:
                        title = " dobra robota "
                        break;
                    case 6:
                        title = " dobrze! "
                        break;
                    default:
                        title = " Musisz jeszcze poćwiczyć "
                }
                title = title + " twój czas to: " + this.reactionTime() + " milisekund"
            }
            return title
        }
    }

}
</script>

<style>

</style>
