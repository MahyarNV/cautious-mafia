<template>
    <div class="container-xxl">
        <div class="row">
            <header>
                <h1>Cautious Mafia</h1>
            </header>
        </div>
        <div class="row">
            <nav>
                <ul>
                    <li>
                        <a href="https://github.com/mahyarnv/" target="_blank"><i class="fab fa-github-square"></i></a>
                    </li>
                    <li>
                        <a href="https://www.linkedin.com/in/mahyarnv/" target="_blank"><i class="fab fa-linkedin"></i></a>
                    </li>
                    <li>
                        <a href="https://www.instagram.com/dev.mahyar/" target="_blank"><i class="fab fa-instagram"></i></a>
                    </li>
                </ul>
            </nav>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss">
    header {
        padding: 4rem 0;

        h1 {
            text-align: center;
            font-weight: 400;
        }
    }

    nav {
        display: flex;
        justify-content: flex-end;

        ul {
            display: flex;
            flex-direction: row-reverse;
            align-items: center;
            font-size: 28px;

            li {
                margin: 0 8px;

                a {
                    &:hover {
                        color: rgba(65, 184, 131, 1);
                    }
                }
            }
        }
    }
</style>