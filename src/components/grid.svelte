<section>
    <slot></slot>
</section>

<style>
    section {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        gap: 30px;
    }
    @media only screen and (max-width: 768px) {
        section {
            grid-template-columns: 1fr;
        }
    }
</style>
