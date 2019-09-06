<template>
  <section class="hero is-success">
    <div class="container">
      <div class="content">
        <nav class="tabs is-boxed is-fullwidth is-large">
          <ul>
            <li class="tab is-active" v-for="(tab, index) in tabs" :key="index" 
            @click="openTab(index)" :class="{ 'is-active': index === tabActive }" style="margin: 0 15px;">
              <a> {{ tab.name }}</a>
            </li>
          </ul>
        </nav>
        <div :id="'tab-' + index" class="content-tab" v-for="(tab, index) in tabs" :key="index"
        v-show="index === tabActive">
          <p>
              {{ tab.content }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>


export default {

    data: function() {
        return {
            tabs: [
                {name: 'tab example 1', content: 'Specification Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industrys standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.'},
                {name: 'tab example 2', content: '2Specification Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industrys standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.'},
                {name: 'tab example 3', content: '3Specification Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industrys standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.'},
            ],
            tabActive : 0
        }
    },
    methods: {
        openTab(evt) {
            this.tabActive = evt;
        }
    }
}
</script>