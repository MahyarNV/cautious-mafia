<template>
    <div class="container-xxl mt-4">
        <div class="row px-2">
            <div class="displayer col-12 col-md-6 col-lg-3">
                <div>
                    <p>Godfather: {{ godfather }}</p>
                    <p>Mafia: {{ mafia }}</p>
                    <p>Citizen: {{ citizen }}</p>
                </div>
            </div>
            <div class="selector col-12 col-md-6 col-lg-9">
                <div>
                    <select id="role" v-model="selected" name="role" @change="roleSelect()">
                        <option selected disabled value="">Select a role</option>
                        <option value="godfather">Godfather</option>
                        <option value="mafia">Mafia</option>
                        <option value="citizen">Citizen</option>
                    </select>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            selected: '',
            godfather: 0,
            mafia: 0,
            citizen: 0,
        }
    },
    methods: {
        roleSelect() {
            switch (this.selected) {
                case 'godfather':
                    this.godfather += 1;
                    break;

                case 'mafia':
                    this.mafia += 1;
                    break;

                case 'citizen':
                    this.citizen += 1;
                    break;
            }
        }
    }
}
</script>
<style lang="scss">
    .displayer {
        height: 400px;
        overflow-y: auto;
        background-color: rgba(0, 0, 0, .1);
        border-radius: 10px;

        div {
            padding: 10px;
        }
    }
</style>