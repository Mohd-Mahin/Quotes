<template>
    <div class="row">
        <div class="col-sm-12">
            <h3>Quotes Added</h3>
            <div class="progress">
                <div class="progress">
                    <div class="progress-bar" role="progressbar" :style="[{ width: (range * 10) + '%', transition }]">
                        {{ range * 10 + '%' }}
                    </div>
                </div>
            </div>
        </div>
                        

    </div>

</template>

<script>
    export default {
        data: function() {
            return {
                transition: '1s width'
            }
        },
        props: {
            range: {
                type: Number,
            }
        }
    }
</script>

<style>

</style>

