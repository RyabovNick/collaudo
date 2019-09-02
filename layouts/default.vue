<template>
  <v-app dark>
    <v-navigation-drawer v-model="drawer" fixed app>
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router>
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Добавить тему',
          to: '/admin/theme'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Добавить тип ответа',
          to: '/admin/type'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Добавить вопрос',
          to: '/admin/question'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Добавить ответ',
          to: '/admin/answer'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Добавить вопросу ответ',
          to: '/admin/question_answer'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Добавить вопросу тип ответа',
          to: '/admin/question_type'
        }
      ],
      title: 'Collaudo'
    }
  }
}
</script>
