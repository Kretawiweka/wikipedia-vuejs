<template>
  <div>
    <navbar/>
    <div class="container">
      <div class="row">
        <b-form>
          <div class="col-8">
            <b-form-input id="search"
              placeholder="Search on Wikipedia .."
              size="lg"
              v-model="searchKey">
            </b-form-input>
          </div>
          <div class="col-2">
            <b-button  @click="onSubmit" size="lg" variant="outline-success">Search..</b-button>
          </div>
        </b-form>
      </div>
      <div class="row">
        <div class="col-8">
          <result-list/>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped src="./index.css"></style>
<script>
import Navbar from '~/components/Navbar'
import ResultList from '~/components/ResultList'
import request from 'superagent'
export default {
  components:{
    'navbar': Navbar,
    'result-list': ResultList
  },
  data(){
    return{
      searchKey:''
    }
  },
  methods: {
    onSubmit(){
      request
        .get('https://id.wikipedia.org/w/api.php?action=query&format=json&gsrlimit=15&generator=search&origin=*&gsrsearch='+this.searchKey)
        .then((result)=>{
          this.listResult(result.body.query.pages)
        })
        .catch((error)=>{
          console.error(error);
        })
    },
    listResult(result){
      console.log(result);
    }
  }
}
</script>
