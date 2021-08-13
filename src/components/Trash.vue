<template>
    <v-row
        class="my-9"
    >
        <v-spacer />
        <v-col
            cols="12"
            sm="12"
            md="12"
            style="text-align:center"

            @dragover.prevent
            @drop="dropOnTrash"

        >
            <v-card
                class="text-center my-10"
                style="background-color: ; border:dashed 5px blue;"
                @dragenter.prevent="dragEnter"
                @dragleave.prevent="dragLeave"
                :class="{'over': isEnterCounter > 0}"
            >
                <span
                    style="color:#cc0033; font-size:20px"
                >
                    Drag & Drop Movie's Comment Here!
                </span>
                <v-icon
                    color="red"
                    style="font-size:50px; "
                >
                    mdi-trash-can
                </v-icon>
            </v-card>
            
        </v-col>
    </v-row>
</template>

<script>
export default ({
    props: {
        droppedMovieId: {
            type: Number,
            default: 0,
        },
    },

    data() {
        return {
            isEnterCounter: 0,
        }
    },

    methods: {
        dragEnter() {
            this.isEnterCounter++
        },
        dragLeave() {
            this.isEnterCounter--
        },
        dropOnTrash() {
            this.isEnterCounter = 0
            this.$emit('deleteMovie', this.droppedMovieId)
        },
    },

    computed: {
        isEntering() {
            return (this.dragDropCount > 0)
        }
    } 
})
</script>
<style scoped>
    .over {
        opacity: 0.5;
    }
</style>
