<template>
<div class="container">
    <div class="row justify-content-center">
        <div class="col-md-8">
            <div class="card">
                <div class="card-header">SheMeansWork Task Component</div>
                <div class="card-body">
                    <form>
                        <div class="mb-3">
                            <label for="exampleInputNumber" class="form-label">Enter Number</label>
                            <input type="number" class="form-control" id="exampleInputNumber" aria-describedby="number">
                            <div class="form-text">Enter Numeric Data.</div>
                        </div>
                        <button type="submit" class="btn btn-primary">Submit</button>
                    </form>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {

    mounted() {
        console.log('Component mounted.')
    }
}
</script>
