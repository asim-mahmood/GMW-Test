<template>
<div class="container">
    <div class="row justify-content-center">
        <div class="col-md-12">
            <div class="card">
                <div class="card-header">SheMeansWork Task Component</div>
                <div class="card-body">
                    <form @submit.prevent="saveNumber">
                        <div class="mb-3 ">
                            <label for="exampleInputNumber" class="form-label">Enter Number</label>
                            <input type="number" v-model="number" class="form-control" id="exampleInputNumber" aria-describedby="number">
                            <div class="form-text">Enter Numeric Data.</div>
                        </div>
                        <button type="submit" class="btn btn-primary">Submit</button>
                    </form>
                </div>
            </div>
            <div class="row p-2 border rounded shadow no-gutters mx-1 mt-3">
                <button type="button" @click="findMax" class="btn btn-success btn-block mb-4">Find Max</button>
                <button type="button" @click="findMin" class="btn btn-danger btn-block">Find Min</button>
                <p>{{ result }}</p>

            </div>

        </div>
    </div>
</div>
</template>

<script>
import axios from 'axios';
export default {

    data() {
        return {
            tasks: [],
            number: 0,
            result: ''
        };
    },
    mounted() {
        this.fetchTasks();
    },
    methods: {
        fetchTasks() {
            axios.get('/tasks/get/data')
                .then(response => {
                    this.tasks = response.data;
                })
                .catch(error => {
                    console.error('Error fetching tasks:', error);
                });
        },
        saveNumber() {
            axios({
                    url: 'tasks',
                    method: 'POST',
                    data: {
                        number: this.number
                    }
                })
                .then(response => {
                    this.tasks.push({"number":response.data.task.number});
                    this.number = 0;
                });
        },
        findMax() {
            const numbers = this.tasks.map(task => task.number);
        
            if (numbers.length > 0) {
                const max = Math.max(...numbers);
                this.result = `Max number: ${max}`;
            } else {
                this.result = 'No valid numbers found in the array.';
            }
        },
        findMin() {
            const numbers = this.tasks.map(task => task.number);
            if (numbers.length > 0) {
                const min = Math.min(...numbers);
                this.result = `Min number: ${min}`;
            } else {
                this.result = 'No valid numbers found in the array.';
            }
        }
    }
};
</script>
