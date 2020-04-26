<template>
    <div class="row">
        <div class="col-sm-12">
            <h3>Quotes Added</h3>
            <div class="progress">
                <div class="progress">
                    <!-- adjust the width of inner div
                    binding to style attribute and dynamically setting width of this div i.e {width: (quoteCount / maxQuotes) * 100 + '%'
                    % is to show percetage symbol-->
                    <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"
                        :style="{width: (quoteCount / maxQuotes) * 100 + '%'}">
                        {{ quoteCount }} / {{ maxQuotes}}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        props: ['quoteCount', 'maxQuotes'] // getting these from parent app.vue
    }
</script>