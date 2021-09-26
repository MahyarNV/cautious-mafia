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
                        <option v-for="option in options" :key="option.value" :value="option.value">
                            {{ option.text }}
                        </option>
                    </select>
                </div>
                <br>
                <div>
                    <div v-for="role in selectedRoles" :key="role.value">{{ role.text }}</div>
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
            options: [
                { text: 'Godfather', value: 'godfather' },
                { text: 'Mafia', value: 'mafia' },
                { text: 'Citizen', value: 'citizen' }
            ],
            selectedRoles: [],
            godfather: 0,
            mafia: 0,
            citizen: 0,
        }
    },
    methods: {
        roleChanged() {
            this.selectedRoles.push(this.options.find(x => x.value === this.selected));
        },
        roleSelect() {
            switch (this.selected) {
                case 'godfather':
                    this.godfather += 1;
                    this.roleChanged();
                    break;

                case 'mafia':
                    this.mafia += 1;
                    this.roleChanged();
                    break;

                case 'citizen':
                    this.citizen += 1;
                    this.roleChanged();
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