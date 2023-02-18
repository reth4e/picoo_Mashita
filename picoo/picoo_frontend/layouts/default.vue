<template>
    <div>
        <header>
            <p class="header-logo"><NuxtLink to="/api">Picoo</NuxtLink></p>
            
            <input type="text" name="tag" placeholder="タグ名検索"  />
            <!-- v-model="tag"-->
            <button @click="">検索</button>
            <!-- searchTag -->
            <button class="btn-mypage btn">
                <!-- ここにイメージ画像 -->
            </button>

            <button class="btn-notification btn"></button>

            <div class="header-menu"  @click="">
                <!-- openMenu -->
                <span class="menu__line--top"></span>
                <span class="menu__line--middle"></span>
                <span class="menu__line--bottom"></span>
                <div :class="{}" class="dropdown">
                    <!-- isOpen -->
                    <ul>
                        <li><NuxtLink to="/api">画像投稿</NuxtLink></li>
                        <li><NuxtLink to="/api/user">マイページ</NuxtLink></li>
                        <li><NuxtLink to="">フォローユーザー</NuxtLink></li>
                        <li><NuxtLink to="">お気に入り画像</NuxtLink></li>
                        <li>ログアウト</li>
                    </ul>
                </div>
            </div>
        </header>
        <Nuxt />
        <footer>
            <small>&copy; 2023 Picoo</small>
        </footer>
    </div>
</template>