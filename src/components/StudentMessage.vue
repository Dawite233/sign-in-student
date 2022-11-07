<template>
    <div>
        <div v-if="student.name">

            <div class=" alert alert-success " v-if="student.present">
                    welcome, {{student.name}}. see you later!
            </div>
            
                <div class="alert alert-info" v-else>
                        GoodBye, {{student.name}}. see you later!
                </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'StudentMessage',
    props: {
        student: object
    }
}

</script>

<style scoped>

</style>
