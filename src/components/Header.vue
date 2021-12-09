<template>
    <div class="row">
        <div class="col-lg-12">
            <label for="">Quote</label>
            <div class="progress">
                <div :style="{ width: (quoteCount / maxQuote) * 100 + '%'}" class="progress-bar" role="progressbar" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100">{{ quoteCount }} / {{ maxQuote }}</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ["maxQuote","quoteCount"]
    }
</script>

