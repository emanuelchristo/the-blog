<script>
    import PostCard from './PostCard.svelte'
</script>

<header>
    <div class="container">
        <h1>The Blog.</h1>
        <div class="options-container">
            <div class="sortby-container">
                <p>Sort by</p>
                <select>
                    <option value="latest">latest</option>
                    <option value="most read">most read</option>
                    <option value="oldest">oldest</option>
                </select>
            </div>
            <div class="serach-container">
                <input type="text" placeholder="search" />
            </div>
        </div>
    </div>
</header>

<main>
    <div class="container">
        <PostCard/>
        <PostCard/>
        <PostCard/>
        <PostCard/>
    </div>
</main>

<footer></footer>

<style>
    h1 {
        margin-top: 50px;
        font-family: Rockwell;
        font-size: 1.4em;
    }

    .container {
        width: 80%;
        margin: 0 auto;
    }

    .options-container {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px;
        border-bottom: 1px solid #000;
    }

    .sortby-container {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    select {
        border: none;
        padding: 10px;
        border-bottom: 1px solid #000;
        margin-left: 15px;
    }

    input {
        border: none;
        padding: 10px;
        border-bottom: 1px solid #000;
    }
</style>
