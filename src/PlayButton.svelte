<script>
    export let disabled;
</script>

<button on:click {disabled} class="button" title="Play a sound">
    <svg
        class="icon"
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="currentColor"
        xmlns="http://www.w3.org/2000/svg"
    >
        <path
            d="M6 7l8-5v20l-8-5v-10zm-6 10h4v-10h-4v10zm20.264-13.264l-1.497 1.497c1.847 1.783 2.983 4.157 2.983 6.767 0 2.61-1.135 4.984-2.983 6.766l1.498 1.498c2.305-2.153 3.735-5.055 3.735-8.264s-1.43-6.11-3.736-8.264zm-.489 8.264c0-2.084-.915-3.967-2.384-5.391l-1.503 1.503c1.011 1.049 1.637 2.401 1.637 3.888 0 1.488-.623 2.841-1.634 3.891l1.503 1.503c1.468-1.424 2.381-3.309 2.381-5.394z"
        />
    </svg>
</button>

<style>
    .button {
        all: unset;
        width: 69vw;
        height: 69vw;
        max-width: 220px;
        max-height: 220px;
        color: #fff;
        cursor: pointer;
        border-radius: 20px;
        transition: opacity, transform 0.45s;
        background-color: rgb(28, 175, 246);
        box-shadow: inset 0px -6px 0px 0px rgba(27, 117, 161, 0.9);
        display: flex;
        align-items: center;
        justify-content: center;
        opacity: 0.8;
    }

    .button:active {
        background-color: rgba(28, 175, 246, 0.9);
    }

    .button:not(:disabled):hover {
        transform: scale(1.05);
    }

    button:disabled {
        opacity: 0.1;
        transform: scale(1.3) translateY(-25px);
    }

    .icon {
        width: 50%;
        height: auto;
    }
</style>
