<template>
  <div class="container">
    <div>
      <h1>
        Name : <span class="name">{{ $route.params.title }}</span>
      </h1>
      <h1>
        Area : <span class="name">{{ $route.params.continent }}</span>
      </h1>
      <h1>
        UpdateTime : <span class="name">{{ $route.params.updatedAt }}</span>
      </h1>
      <div class="imageWarp">
        <h3>详情介绍:{{ $route.params.description }}</h3>
        <img :src="$route.params.description" alt="" srcset="" />
      </div>
      <p><NLink to="/special" class="button--grey">返回上一页</NLink></p>
    </div>
  </div>
</template>

<script>
export default {
  asyncData() {
    // 打包的一刹那,process.server变成了true,常规情况下是false也就是client客户端模式
    return {
      name: process.server ? "server" : "client",
    };
  },
  // async asyncData({ params, redirect }) {
  //   const mountains = await fetch(
  //     "https://api.nuxtjs.dev/mountains"
  //   ).then((res) => res.json());
  //   let array1 = [];
  //   const filteredMountain = mountains.find(
  //     (el) =>
  //       el.image ===
  //       "https://upload.wikimedia.org/wikipedia/commons/thumb/9/91/Wonder_Lake_and_Denali.jpg/600px-Wonder_Lake_and_Denali.jpg"
  //   );
  //   if (filteredMountain) {
  //     return {
  //       continent: filteredMountain.image,
  //       mountain: mountains,
  //     };
  //   } else {
  //     // redirect("/");
  //     alert(666);
  //   }
  // },
};
</script>

<style scoped>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
h1 {
  font-weight: 400;
}
.imageWarp {
  /* border: 1px solid red; */
  width: 100%;
}
.name {
  color: #00C48D;
}
p {
  margin-top: 20px;
}
</style>
