<template>
    <div>
        <div class="alert alert-danger" v-show="errors.length">
            <li v-for="error in errors"  v-bind:key="error" > {{ error }}</li>
        </div>
        <div class="card add-student m-2 p-2">
            <h4 class="card-title">Add new student</h4>
             <div class="form-group">
                <label for="name">Name</label>
                <input id="name" class="form-control" v-model.trim="newStudentName" >
            </div>
            <div class="form-group">
                <label for="starID">Star ID</label>
                <input id="starID" class="form-control" v-model.trim="newStarID " >
            </div>
            <button class="btn btn-primary" v-on:click="addStudent">Add</button >
            </div>
    </div>
</template>

<script>
export default {
    name: 'NewStudentForm',
    emits: ['student-added'], // Document events this componenet emits
    data() {
        return {
            newStudentName: '',
            newStarID: '',
            errors: []
        }
    }, 
    methods: {
        addStudent() {
            this.errors = [] // clean errors array

            if (this.newStudentName && this.newStarID) {
                let student = {name: this.newStudentName, starID: this.newStarID, present: false}
           

                // TODO emit message to parent with new student
                this/this.$emit('student-added', student )

            this.newStudentName = ' '
            this.newStarID = ''
        } else {
            this.errors.push('Name and StarID are required')

        }
    }
}
}

</script>

<style scoped>

</style>