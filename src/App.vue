<template>
  <div>
    <MyForm />
    <div>{{ greet }} {{ name }}</div>
    <div v-html="role"></div>
    <div v-text="name"></div>
    <div v-html="hack"></div>
    <h2 :id="headingId">Heading</h2>
    <button :disabled="isDisabled">Bind</button>
    <h2 class="underline">Underlined text</h2>
    <h2 class="underline" :class="status">Status</h2>
    <h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
    <h2 :class="isSoldout ? 'sold-out' : 'new'">Soldout? movie</h2>
    <h2 :class="['new', 'promoted']">Newly promoted movie</h2>
    <h2 :class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">
      Array conditional movie
    </h2>
    <h2
      :class="{
        promoted: isPromoted,
        new: !isSoldout,
        'sold-out': isSoldout,
      }"
    >
      Object conditional movie
    </h2>
    <h2
      :style="{
        color: highlightColor,
        'font-size': headerSize + 'px',
        padding: '20px',
      }"
    >
      Inline Style
    </h2>
    <h2 :style="headerStyleObject">Style Object</h2>
    <div :style="[baseStyleObject, successStyleObject]">Success Style</div>
    <div :style="[baseStyleObject, dangerStyleObject]">Danger Style</div>
    <h2 v-if="num === 0">This number is Zero</h2>
    <h2 v-else-if="num < 0">This number is Negative</h2>
    <h2 v-else-if="num > 0">This number is Positive</h2>
    <h2 v-else>Not a number</h2>
    <div v-if="display">
      <h2>Anirudh</h2>
      <h2>Codevolution</h2>
      <h2>Vue</h2>
    </div>
    <h2 v-show="showElement">Using v-show</h2>
    <h2 v-if="showElement">Using v-if</h2>
    <h2 v-for="(name, index) in names" :key="name">{{ index }} {{ name }}</h2>
    <h2 v-for="name in fullNames" :key="name.first">
      {{ name.first }} {{ name.last }}
    </h2>
    <div v-for="actor in actors" :key="actor.name">
      <h2>{{ actor.name }}</h2>
      <h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>
    </div>
    <h2 v-for="(value, key, index) in myInfo" :key="value">
      {{ index }} {{ key }} {{ value }}
    </h2>
    <template v-for="name in names" :key="name">
      <h2 v-if="name === 'Anirudh'">{{ name }}</h2>
      <hr />
    </template>
    <h2>{{ 2 + 3 + 5 }}</h2>
    <h2>{{ 8 + 6 + 10 }}</h2>
    <h2>Add method - {{ add(2, 3, 5) }}</h2>
    <h2>Add method - {{ add(4, 7, 9) }}</h2>
    <h2>Multiply method - {{ multiply(baseValue) }}</h2>
    <h2>{{ name }}</h2>
    <div>
      <button v-on:click="changeName">Change name</button>
    </div>
    <h2>{{ count }}</h2>
    <button v-on:click="count += 1">Increment</button>
    <button @click="count += 1">Increment</button>
    <button v-on:click="count -= 1">Decrement</button>
    <button @click="count -= 1">Decrement</button>
    <h2 v-once>{{ name }}</h2>
    <button @click="name = 'Batman'">Change name</button>
    <h2 v-pre>{{ name }}</h2>
    <h2>Fullname - {{ firstName }} {{ lastName }}</h2>
    <h2>Computed fullname - {{ fullName }}</h2>
    <button @click="changeFullname">Change Fullname</button>
    <h2>
      Total -
      {{ items.reduce((total, curr) => (total = total + curr.price), 0) }}
    </h2>
    <button @click="items.push({ id: 4, title: 'Keyboard', price: 50 })">
      Add item
    </button>
    <h2>Computed Total - {{ total }}</h2>
    <h2>Method Total = {{ getTotal() }}</h2>
    <input type="text" v-model="country" />

    <template v-for="item in items" :key="item.id">
      <h2 v-if="item.price > 100">{{ item.title }} {{ item.price }}</h2>
    </template>
    <h2 v-for="item in expensiveItems" :key="item.id">
      {{ item.title }} {{ item.price }}
    </h2>
    <h2>Volume Tracker (0-20)</h2>
    <h3>Current Volume - {{ volume }}</h3>
    <div>
      <button @click="volume += 2">Increase</button>
      <button @click="volume -= 2">Decrease</button>
    </div>
    <input type="text" v-model="movie" />
    <input type="text" v-model="movieInfo.title" />
    <input type="text" v-model="movieInfo.actor" />
    <div>
      <button @click="movieList.push('Wonder Woman')">Add Movie</button>
    </div>
    <MyGreet name="Avanti" heroName="Batman" />
    <MyGreet name="Avinash" heroName="Superman" />
    <MyGreet name="Namita" heroName="Wonder Woman" />
    <MyGreet :name="name" :heroName="greet" />
    <MyArticle
      id="my-article"
      title="Article Title"
      :likes="50"
      :isPublished="true"
    />
    <h3>AppComponent username {{ name }}</h3>
    <ComponentC />
    <button @click="showPopup = true">Show Popup</button>
    <PopUp v-show="showPopup" @close="closePopup" />
    <MyInput v-model="name" /> -->
    <MyCard></MyCard>
    <MyCard>Card congtent</MyCard>
    <MyCard><h2>card content</h2></MyCard>
    <MyCard>
      <img src="https://picsum.photos/200" />
    </MyCard>

    <MyCard>
      <template v-slot:header>
        <h3>Header</h3>
      </template>
      <template v-slot:default>
        <img src="https://picsum.photos/200" />
      </template>
      <template v-slot:footer>
        <h3>View Details</h3>
      </template>
    </MyCard>
    -->
    <NameList>
      <template v-slot:default="slotProps">
        {{ slotProps.firstName }} {{ slotProps.lastName }}
      </template>
    </NameList>

    <NameList>
      <template v-slot:default="slotProps">
        {{ slotProps.lastName }} {{ slotProps.firstName }}
      </template>
    </NameList>
    <h4>App Component text</h4>
    <ChildStyles />
    <button @click="activeTab = 'TabA'">Tab A</button>
    <button @click="activeTab = 'TabB'">Tab B</button>
    <button @click="activeTab = 'TabC'">Tab C</button>

    <keep-alive>
      <component :is="activeTab" />
    </keep-alive>
    <TabA v-if="activeTab === 'TabA'" />
    <TabB v-if="activeTab === 'TabB'" />
    <TabC v-if="activeTab === 'TabC'" />
    <teleport to="#portal-root">
      <MyPortal />
    </teleport>
    <PostList />
    <CreatePost />
    <TemplateRef />
    <ClickCounter />
    <HoverCounter />
    <MyData />
    <DemoOne />
    <DemoTwo />
    <MyMethod />
    <VModel />
    <MyComputed />
    <MyWatch />
    <ProvideInject />
    <LifecycleC />
    <LifecycleO />
    <TemplateRefs />
    <MyPerson />
  </div>
</template>

<script>
import MyPerson from "./Components/MyPerson.vue";
import TemplateRefs from "./Components/TemplateRefs.vue";
import LifecycleC from "./Components/LifecycleC.vue";
import LifecycleO from "./Components/LifecycleO.vue";
import ProvideInject from "./Components/ProvideInject.vue";
import MyWatch from "./Components/MyWatch.vue";
import MyComputed from "./Components/MyComputed.vue";
import VModel from "./Components/VModel.vue";
import MyMethod from "./Components/MyMethod.vue";
import DemoOne from "./Components/DemoOne.vue";
import DemoTwo from "./Components/DemoTwo.vue";
import MyData from "./Components/MyData.vue";
import ClickCounter from "./Components/ClickCounter.vue";
import HoverCounter from "./Components/HoverCounter.vue";
import TemplateRef from "./Components/TemplateRef.vue";
import MyParent from "./Components/MyParent.vue";
import PostList from "./Components/PostList.vue";
import CreatePost from "./Components/CreatePost.vue";
import MyPortal from "./Components/MyPortal.vue";
import ChildStyles from "./Components/ChildStyles.vue";
import TabA from "./Components/TabA.vue";
import TabB from "./Components/TabB.vue";
import TabC from "./Components/TabC.vue";
import NameList from "./Components/NameList.vue";
import MyCard from "./Components/MyCard.vue";
import MyForm from "./MyForm.vue";
import MyGreet from "./Components/MyGreet.vue";
import MyArticle from "./Components/MyArticle.vue";
import ComponentC from "./Components/ComponentC.vue";
import PopUp from "./Components/PopUp.vue";
import MyInput from "./Components/MyInput.vue";

export default {
  components: {
    ClickCounter,
    HoverCounter,
    MyPerson,
    TemplateRefs,
    LifecycleC,
    LifecycleO,
    ProvideInject,
    MyWatch,
    MyComputed,
    VModel,
    MyMethod,
    DemoOne,
    DemoTwo,
    MyData,
    TemplateRef,
    MyParent,
    PostList,
    CreatePost,
    MyPortal,
    ChildStyles,
    TabA,
    TabB,
    TabC,
    NameList,
    MyCard,
    MyForm,
    MyGreet,
    MyArticle,
    PopUp,
    ComponentC,
    MyInput,
  },
  name: "App",
  data() {
    return {
      activeTab: "TabA",
      showPopup: false,
      greet: "Hello",
      name: "Anirudh",
      role: "<h1>Developer</h1>",
      hack: `<a href="#" onclick="alert('You have been hacked!!')" >Win a prize!</a>`,
      headingId: "heading",
      isDisabled: false,
      status: "danger",
      isPromoted: true,
      isSoldout: true,
      highlightColor: "orange",
      headerSize: 50,
      headerStyleObject: {
        color: "orange",
        fontSize: "50px",
        padding: "20px",
      },
      baseStyleObject: {
        fontSize: "50px",
        padding: "10px",
      },
      successStyleObject: {
        color: "green",
        backgroundColor: "lightgreen",
        border: "1px solid green",
        padding: "20px",
      },
      dangerStyleObject: {
        color: "darkred",
        backgroundColor: "red",
        border: "1px solid darkred",
      },
      num: 5,
      display: true,
      showElement: true,
      names: ["Avanti", "Avinash", "Anirudh"],
      fullNames: [
        { first: "Avanti", last: "Panda" },
        { first: "Avinash", last: "Panda" },
        { first: "Anirudh", last: "Panda" },
      ],
      actors: [
        {
          name: "Christian Bale",
          movies: ["Batman", "The Prestige"],
        },
        {
          name: "Di Caprio",
          movies: ["Titanic", "Inception"],
        },
      ],
      myInfo: {
        name: "Anirudh",
        channel: "Codevolution",
        course: "Vue 3",
      },
      baseMultiplier: 5,
      baseValue: 2,
      count: 0,
      firstName: "Anirudh",
      lastName: "Panda",
      items: [
        {
          id: 1,
          title: "TV",
          price: 100,
        },
        {
          id: 2,
          title: "Phone",
          price: 200,
        },
        {
          id: 3,
          title: "Laptop",
          price: 300,
        },
      ],
      country: "",
      volume: 0,
      movie: "Batman",
      movieInfo: {
        title: "",
        actor: "",
      },
      movieList: ["Batman", "Superman"],
    };
  },
  methods: {
    closePopup(name) {
      this.showPopup = false;
      console.log("name", name);
    },
    add(a, b, c) {
      return a + b + c;
    },
    multiply(num) {
      return num * this.baseMultiplier;
    },
    changeName() {
      this.name = "Batman";
    },
    getTotal() {
      console.log("getTotal Method");
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        0
      );
    },
    changeFullname() {
      this.fullName = "Avanti Panda";
    },
  },
  computed: {
    fullName: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        const names = value.split(" ");
        this.firstName = names[0];
        this.lastName = names[1];
      },
    },
    total() {
      console.log("getTotal computed property");
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        0
      );
    },
    expensiveItems() {
      return this.items.filter((item) => item.price > 100);
    },
  },
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert(
          "Listening to a high volume for a long time may damage your hearing"
        );
      }
    },
    movie: {
      handler(newValue) {
        console.log(`Calling API with movie name = ${newValue}`);
      },
      immediate: true,
    },
    movieInfo: {
      handler(newValue) {
        console.log(
          `Calling API with movie title = ${newValue.title} and actor = ${newValue.actor}`
        );
      },
      deep: true,
    },
    movieList: {
      handler(newValue) {
        console.log(`Updated list ${newValue}`);
      },
      deep: true,
    },
  },
  provide() {
    return {
      username: this.name,
    };
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}

h4 {
  color: orange;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: olivedrab;
}

.sold-out {
  color: red;
}
</style>
