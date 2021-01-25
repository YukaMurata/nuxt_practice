<template>
  <section class="component">
    <div>
      <h1 :style="{ color: group.color }">{{ group.groupName }}</h1>
    </div>
    <ul class="member-list">
      <li
        class="member-list__item"
        v-for="member in group.memberList"
        :key="member.index"
      >
        {{ member[2] }}
      </li>
    </ul>

    <nuxt-link to="/">トップへ</nuxt-link>
  </section>
</template>

<script>
export default {
  asyncData() {
    const users = require(`~/assets/json/member.json`);
    const group = users["morning"];
    return {
      group
    };
  }
};
</script>

<style lang="scss">
.component {
  text-align: center;
}
.member-list {
  .member-list__item {
    text-align: left;
  }
}
</style>
