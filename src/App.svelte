<script>
    import PostCard from "./PostCard.svelte";
    import Loader from "./Loader.svelte";

    let bdy =
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum ut auctor dolor. Nullam ornare leo massa, et tempus felis viverra a. Duis aliquet suscipit elit vestibulum accumsan. Morbi condimentum consequat augue, a vehicula nunc mattis non. Quisque nec leo id neque facilisis convallis. Nam maximus sed sem id tincidunt. Aenean libero sem, tempus sed risus eget, tristique tincidunt mi. Nulla aliquet nibh et sollicitudin blandit.";
    let blogPosts = [
        {
            title: "Is it time to regulate Big Tech?",
            body: bdy,
            date: "Today",
        },
        {
            title: "This is a wonderful title",
            body: bdy,
            date: "3 Jan 2021",
        },
        {
            title: "Yet another title",
            body: bdy,
            date: "3 Feb 2021",
        },
    ];

    const reachedBottom = () => {
        let windowRelativeBottom = document.documentElement.getBoundingClientRect()
            .bottom;
        if (windowRelativeBottom < document.documentElement.clientHeight + 200)
            loadPosts();
    };

    let loadingPosts = false;

    function loadPosts() {
        if(!loadingPosts) {
            loadingPosts = true
            for (let i = 0; i < 5; i++) {
            blogPosts = [...blogPosts, {
                title: "Is it time to regulate Big Tech?",
                body: bdy,
                date: "Today",
            }];
            loadingPosts = false;
            }
        }
    }

    window.onscroll = reachedBottom;
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
        {#each blogPosts as post}
            <PostCard title={post.title} body={post.body} date={post.date} />
        {/each}
    </div>
</main>

<footer>
    <div class="loader-wrapper">
        <Loader />
    </div>
</footer>

<style>
    header .container {
        position: fixed;
        top: 0;
        right: 0;
        left: 0;
        background-color: #fff;
    }

    main .container{
        margin-top: 200px;
        border-top: 1px solid #000;

    }

    h1 {
        padding-top: 50px;
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
    }

    .sortby-container {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    select {
        all: unset;
        border: none;
        padding: 10px;
        border-bottom: 1px solid #000;
        margin-left: 15px;
    }

    input {
        all: unset;
        border: none;
        padding: 10px;
        border-bottom: 1px solid #000;
    }

    .loader-wrapper {
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 30px 0;
    }
</style>
