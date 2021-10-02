<template>
    <div class="container-xxl mt-4">
        <div class="row px-2">
            <div class="displayer col-12 col-md-6 col-lg-3">
                <div>
                    <p v-for="option in options" :key="option.value">
                        {{ option.text }}: {{ option.n }}
                    </p>
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
                { text: 'Godfather', value: 'godfather', n: 0 },
                { text: 'Mafia', value: 'mafia', n: 0 },
                { text: 'Citizen', value: 'citizen', n: 0 }
            ],
            selectedRoles: [],
        }
    },
    methods: {
        roleChanged() {
            const role = this.options.find(x => x.value === this.selected);
            if (!this.selectedRoles.find(x => x.value === role.value)) {
                this.selectedRoles.push({text: role.text, value: role.value});
            }
        },
        roleSelect() {
            const role = this.options.find(element => element.value === this.selected)
            role.n += 1;
            this.roleChanged();
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