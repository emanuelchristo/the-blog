<script>
    export let title
    export let body
    export let date
</script>

<div class="contianer">
    <div class="left">
        <p>{date}</p>
        <h2>{title}</h2>
    </div>
    <div class="right">
        <p>{body}</p>
        <div class="more-wrapper"><a href="body">more</a></div>
    </div>
</div>

<style>
    .contianer {
        display: flex;
        padding: 40px 25px 100px 25px;
        border-bottom: 1px solid #000;
    }
    
    .left {
        width: 30%;
    }

    .right {
        width: 70%;
        margin-left: 100px;
    }

    .left p {
        all: unset;
        color: #ff0000;
        font-size: 10pt;
    }

    h2 {
        font-family: Rockwell;
        margin: 0;
        margin-top: 15px;
        font-size: 2.2em;
    }

    .right p {
        margin: 0;
        margin-top: 30px;
        letter-spacing: 0.5px;
    }

    a {
        color: #0062ff;
    }

    .more-wrapper {
        margin-top: 10px;
    }
</style>