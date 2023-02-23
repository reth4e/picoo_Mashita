<template>
    <div>
        <header>
            <p class="header-logo"><NuxtLink to="/" class="link" style="text-decoration: none; color: #000;">Picoo</NuxtLink></p>
            
            <input type="text" name="tag" placeholder="タグ名検索" v-model="tag" />
            <button @click="searchTag">検索</button>

            <button class="btn-mypage btn">
                <!-- ここにイメージ画像 -->
                マイページ
            </button>

            <button class="btn-notification btn">通知</button>

            <div class="header-menu"  @click="openMenu">
                <span class="menu_line-top"></span>
                <span class="menu_line-middle"></span>
                <span class="menu_line-bottom"></span>
            </div>
            <div class="dropdown" :class="{isOpen}">
                <ul>
                    <li><NuxtLink to="/" style="text-decoration: none; color: #000;">画像投稿</NuxtLink></li>
                    <li><NuxtLink to="/api/user" style="text-decoration: none; color: #000;">マイページ</NuxtLink></li>
                    <li><NuxtLink to="/api/user/follows" style="text-decoration: none; color: #000;">フォローユーザー</NuxtLink></li>
                    <li><NuxtLink to="/api/user/favorites" style="text-decoration: none; color: #000;">お気に入り画像</NuxtLink></li>
                    <li><NuxtLink to="/api/popular" style="text-decoration: none; color: #000;">人気ユーザー・画像</NuxtLink></li>
                    <li>ログアウト</li>
                </ul>
            </div>
            
        </header>
        
        <Nuxt />

        <footer>
            <small>&copy; 2023 Picoo</small>
        </footer>
    </div>
</template>

<script>
export default{
    data() {
        return {
            tag: "",
            isOpen: false,
        };
    },

    methods: {
        openMenu() {
            this.isOpen = !this.isOpen
        },

        searchTag(){
        }
    },
    
};
</script>

<style>
li {
    list-style: none;
}

.header-menu {
    display: inline-block;
    width: 36px;
    height: 32px;
    cursor: pointer;
    position: relative;
    left: 20px;
    top: 20px;
}

.menu_line-top,
.menu_line-middle,
.menu_line-bottom {
    display: inline-block;
    width: 100%;
    height: 4px;
    background-color: #000;
    position: absolute;
}

.menu_line-top {
    top: 0;
}

.menu_line-middle {
    top: 14px;
}

.menu_line-bottom {
    bottom: 0;
}

.dropdown {
    display: none;
    width: 30vw;
    padding: 0;
    list-style-type: none;
    background-color: #007db9;
}

.isOpen {
    display: block;
}
</style>