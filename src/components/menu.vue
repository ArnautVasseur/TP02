<template>
    <div class="nav dark:bg-[#222]">
      <ul>
        <li class="list">
          <RouterLink to="/offres">
            <span class="icon"><i class="fa-solid fa-house dark:text-white"></i></span>
            <span class="title border-[#55BC9F] border-2 dark:text-white dark:bg-[#222]">Listes</span>
            <span class="box w-16 h-16 -mt-1 border-2 border-transparent hover:border-white absolute rounded-t-full"></span>
          </RouterLink>
        </li>
        <li class="list">
          <RouterLink to="/agent">
            <span class="icon"><i class="fa-solid fa-user dark:text-white"></i></span>
            <span class="title border-[#55BC9F] border-2 dark:text-white dark:bg-[#222]">Agents</span>
            <span class="box w-16 h-16 -mt-1 border-2 border-transparent hover:border-white absolute rounded-full"></span>
          </RouterLink>
        </li>
        <li class="list">
          <RouterLink to="/commune">
            <span class="icon"><i class="fa-solid fa-building dark:text-white"></i></span>
            <span class="title border-[#55BC9F] border-2 dark:text-white dark:bg-[#222]">Communes</span>
            <span class="box w-16 h-16 -mt-1 border-2 border-transparent hover:border-white absolute rounded-full"></span>
          </RouterLink>
        </li>
        <li class="list">
          <RouterLink to="/quartier">
            <span class="icon"><i class="fa-solid fa-road dark:text-white"></i></span>
            <span class="title border-[#55BC9F] border-2 dark:text-white dark:bg-[#222]">Quartiers</span>
            <span class="box w-16 h-16 -mt-1 border-2 border-transparent hover:border-white absolute rounded-full"></span>
          </RouterLink>
        </li>
        <li class="list">
          <RouterLink to="/modifier">
            <span class="icon"><i class="fa-solid fa-gear dark:text-white"></i></span>
            <span class="title border-[#55BC9F] border-2 dark:text-white dark:bg-[#222]">Modifier Offres</span>
            <span class="box w-16 h-16 -mt-1 border-2 border-transparent hover:border-white absolute rounded-b-full"></span>
          </RouterLink>
        </li>
      </ul>
    </div>
</template>

<style>
.nav{
    position: fixed;
    right: 30px;
    width: 70px;
    height: 350px;
    background-color: white;
    border-radius: 35px;
    box-shadow: 0 0px 25px rgba(255, 255, 255, 0.1);
}

.nav ul{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    display: flex;
    flex-direction: column;
    
}

.nav ul li{
    position: relative;
    list-style: none;
    width: 70px;
    height: 70px;
    z-index: 1;
}

.nav ul li a{
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    text-align: center;
    color: #333;
    font-weight: 500;
}

.nav ul li a .icon{
    position: relative;
    display: block;
    line-height: 75px;
    text-align: center;
}

.nav ul li a .icon i{
    font-size: 24px;
}

.nav ul li a .title{
    position: absolute;
    top: 50%;
    right: 70px;
    transform: translateY(-50%);
    padding: 5px 10px;
    border-radius: 6px;
    transition: 0.5s;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    opacity: 0;
    visibility: hidden;
}

.nav ul li a .box:hover{
  transition-duration: 500ms;
  border-width: 2px;
}

.nav ul li:hover a .title{
    opacity: 1;
    visibility: visible;
    transform: translateY(-50%) translateX(-25px);
}
</style>