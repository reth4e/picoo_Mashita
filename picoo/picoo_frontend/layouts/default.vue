<template>
    <div>
        <header>
            <p class="header-logo"><NuxtLink to="/api">Picoo</NuxtLink></p>
            
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
                    <li><NuxtLink to="/api" class="menu-link">画像投稿</NuxtLink></li>
                    <li><NuxtLink to="/api/user" class="menu-link">マイページ</NuxtLink></li>
                    <li><NuxtLink to="/api/user/follows" class="menu-link">フォローユーザー</NuxtLink></li>
                    <li><NuxtLink to="/api/user/favorites" class="menu-link">お気に入り画像</NuxtLink></li>
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
.menu-link {
    text-decoration: none;
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