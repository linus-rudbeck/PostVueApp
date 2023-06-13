 <template>  
    <div>
      <span class="posts" v-for="d in posts" :key="d">
        <span style="display: flex; flex-direction: column">
          <p><b>{{d.title}} </b>| Date: {{d.date}}</p> <br/>
          <p class="blog-text">{{d.content}}</p>
          <p class="blog-text" v-if="d.show">{{d.moreContent}}</p>
       </span>
         <button v-if="!d.show" @click="d.show = true"> Show More Text</button>
         <button v-if="d.show" @click="d.show = false"> Show Less</button>

          <router-link  :to="{name: 'post', params: {id: d.id, title: d.title, date: d.date, content: d.content, moreContent: d.moreContent} }">
             <button>Show Post</button>
          </router-link>  
     </span>       
    </div>
  </template>
  <script>
  export default {
    data() {
      return {
        posts: [
         { 
           id: 1,
           date:"23-06-08",
           title:"On the other hand...",
           content:"On the other hand, we denounce with righteous indignation and dislike men who are so beguiled and demoralized by the charms of pleasure of the moment, so blinded by desire, that they cannot foresee the pain and trouble that are bound to ensue; and equal blame belongs to those who fail in their duty through weakness of will, which is the same as saying through shrinking from toil and pain. These cases are perfectly simple and easy to distinguish. ",
           moreContent:"In a free hour, when our power of choice is untrammelled and when nothing prevents our being able to do what we like best, every pleasure is to be welcomed and every pain avoided. But in certain circumstances and owing to the claims of duty or the obligations of business it will frequently occur that pleasures have to be repudiated and annoyances accepted. The wise man therefore always holds in these matters to this principle of selection: he rejects pleasures to secure other greater pleasures, or else he endures pains to avoid worse pains.",
           show: false
         },
         { 
           id: 2,
           date:"23-06-05",
           title:"But I must explain to you..",
           content:"But I must explain to you how all this mistaken idea of denouncing pleasure and praising pain was born and I will give you a complete account of the system, and expound the actual teachings of the great explorer of the truth, the master-builder of human happiness. No one rejects, dislikes, or avoids pleasure itself, because it is pleasure, but because those who do not know how to pursue pleasure rationally encounter consequences that are extremely painful. Nor again is there anyone who loves or pursues or desires to obtain pain of itself, because it is pain, but because occasionally circumstances occur in which toil and pain can procure him some great pleasure.",
           moreContent:"To take a trivial example, which of us ever undertakes laborious physical exercise, except to obtain some advantage from it? But who has any right to find fault with a man who chooses to enjoy a pleasure that has no annoying consequences, or one who avoids a pain that produces no resultant pleasure?",
           show: false
          },
         {
           id: 3,
           date:"23-06-05",
           title:"On the other hand...",
           content:"On the other hand, we denounce with righteous indignation and dislike men who are so beguiled and demoralized by the charms of pleasure of the moment, so blinded by desire, that they cannot foresee the pain and trouble that are bound to ensue; and equal blame belongs to those who fail in their duty through weakness of will, which is the same as saying through shrinking from toil and pain. These cases are perfectly simple and easy to distinguish. ",
           moreContent:"In a free hour, when our power of choice is untrammelled and when nothing prevents our being able to do what we like best, every pleasure is to be welcomed and every pain avoided. But in certain circumstances and owing to the claims of duty or the obligations of business it will frequently occur that pleasures have to be repudiated and annoyances accepted. The wise man therefore always holds in these matters to this principle of selection: he rejects pleasures to secure other greater pleasures, or else he endures pains to avoid worse pains.",
           show: false
         },
         { 
           id: 4,
           date:"23-05-24",
           title:"But I must explain to you..",
           content:"But I must explain to you how all this mistaken idea of denouncing pleasure and praising pain was born and I will give you a complete account of the system, and expound the actual teachings of the great explorer of the truth, the master-builder of human happiness. No one rejects, dislikes, or avoids pleasure itself, because it is pleasure, but because those who do not know how to pursue pleasure rationally encounter consequences that are extremely painful. Nor again is there anyone who loves or pursues or desires to obtain pain of itself, because it is pain, but because occasionally circumstances occur in which toil and pain can procure him some great pleasure.",
           moreContent:"To take a trivial example, which of us ever undertakes laborious physical exercise, except to obtain some advantage from it? But who has any right to find fault with a man who chooses to enjoy a pleasure that has no annoying consequences, or one who avoids a pain that produces no resultant pleasure?",
           show: false
          },
         { 
           id: 5,
           date:"23-05-22",
           title:"On the other hand...",
           content:"On the other hand, we denounce with righteous indignation and dislike men who are so beguiled and demoralized by the charms of pleasure of the moment, so blinded by desire, that they cannot foresee the pain and trouble that are bound to ensue; and equal blame belongs to those who fail in their duty through weakness of will, which is the same as saying through shrinking from toil and pain. These cases are perfectly simple and easy to distinguish. ",
           moreContent:"In a free hour, when our power of choice is untrammelled and when nothing prevents our being able to do what we like best, every pleasure is to be welcomed and every pain avoided. But in certain circumstances and owing to the claims of duty or the obligations of business it will frequently occur that pleasures have to be repudiated and annoyances accepted. The wise man therefore always holds in these matters to this principle of selection: he rejects pleasures to secure other greater pleasures, or else he endures pains to avoid worse pains.",
           show: false
          }
        ]
      }      
    },
    }
  </script>
  <style scoped>
  .blog-text {
    max-width: 900px;
    align-self: center;
  }
  .posts {
    display: flex; 
    flex-direction: row;
    justify-content: space-between;
    margin: 16px;
    border-bottom: 2px solid #42b9836e;
  }
  button {
    background-color: #42b983;
    color: #fff;
    border: none;
    font-weight: 600;
    border-radius: 3px;
    padding: 10px 25px;
    height: 40px;
    margin-top: 100px;
  }
  </style>