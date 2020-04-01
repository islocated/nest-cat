<script>
    export let image;
</script>

<style>
    .cat {
        padding: 10px;
        border: 1px solid #333;
        border-radius: 5px;
        box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.1);
        background: #ccc;
        text-align: center;
    }

    img {
        border-radius: 5px;
        width: 100%;
    }
</style>

<div class="cat">
    <img src={image} alt="Cat Picture" />
</div>