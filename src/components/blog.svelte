<script>
    export let blog;
    let show = false;
    const toggleKeywords = () => {
        show = !show
    }
</script>

<div class="blog">
    <div class="blog__title">
        <div class="blog__title-logo">
            <img alt={blog.blog} src={blog.logo} />
        </div>
        <div class="blog__title-name">
            <h3>{blog.blog}</h3>
            {#if blog.name}
                <p>ينتمي إلي <b>{blog.name}</b></p>
            {/if}
        </div>
    </div>
    <p class="blog__desc">{blog.description}</p>
    <div class="blog__actions">
        <div class="blog__actions-action">{blog.emoji}</div>
        <div class="blog__actions-action" on:click={toggleKeywords}>🗂</div>
        <a class="blog__actions-action" href={blog.url} target="_blank">🔗</a>
    </div>
    <div class="blog__keywords {show? 'blog__keywords--show': ''}">
        {#each blog.keywords as keyword}
            <span class="blog__keywords-keyword">{keyword}</span>
        {/each}
    </div>
    
</div>

<style lang="scss">
    .blog {
        position: relative;
        overflow: hidden;
        display: flex;
        align-items: stretch;
        justify-content: space-between;
        flex-direction: column;
        background-color: white;
        padding: 30px;
        background-color: rgba(255, 255, 255, .1);
        border-radius: 5px;
        &__title {
            display: flex;
            align-items: flex-start;
            justify-content: flex-start;
            &-logo {
                display: flex;
                width: 50px;
                height: 50px;
                align-items: center;
                justify-content: center;
                object-fit: cover;
                border-radius: 3px;
                overflow: hidden;
                background-color: white;
                img {
                    width: 100%;
                    height: 100%;
                }
            }
            &-name {
                margin-inline-start: 15px;
                h3 {
                    margin: 0;
                }
                p {
                    margin: 10px 0 0 0;
                }
            }
        }
        &__actions {
            display: flex;
            align-items: center;
            border-top: 2px solid #292d32;
            margin: 0 -30px -30px;
            position: relative;
            z-index: 3;
            &-action {
                transition: .2s;
                flex: 1;
                padding: 5px 0;
                text-align: center;
                font-weight: 300;
                font-size: 23px;
                text-decoration: none;
                cursor: pointer;
                &:not(:last-child) {
                    border-left: 2px solid #292d32;
                }
                &:hover {
                    background-color: #292d32;
                }
            }
        }
        &__keywords {
            position: absolute;
            left: 0;
            top: 100%;
            width: 100%;
            padding: 30px;
            height: 100%;
            transition: .5s;
            z-index: 2;
            background-color: #f2f2f2;
            color: #292d32;
            box-sizing: border-box;
            overflow-y: auto;
            &--show {
                top: 0;
            }
            &-keyword {
                background-color: rgba(0, 0, 0, 0.09);
                display: inline-block;
                padding: 5px 10px;
                margin-inline-end: 10px;
                margin-block-end: 10px;
            }
        }
    }

</style>
