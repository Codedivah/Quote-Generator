
<template>
<div>{{greet}} {{ name }}</div>
<div v-html="course"></div>
<h2 class=underline v-bind:id="headingId">Heading</h2>
<button v-bind:disabled="isDisabled">Submit</button>
<h2 v-bind:class="status">Status</h2>
<h2 v-bind:class=" isPromoted && 'promoted'">Promoted Movies</h2>
<h2 v-bind:class="isSoldout ?'soldout': 'new'">Soldout ?Movie</h2>
<h2  v-bind:class="['new','promoted']">Newly promoted movie Array Binding</h2>
<h2 v-bind:class="{
  promoted: isPromoted,
  new: !isSoldout,
 'sold-out': isSoldout, 

}">Object conditonal movie</h2>

<h2 v-bind:style="{
  color: highlightColor,
  fontSize: headerSize + 'px'
}">Inline style</h2>
<h2 v-bind:style="headerStyleObject">Object Style</h2>
</template>




<script>
export default {
name:'App',
data(){
  return{
    name:"Fatimah",
    greet:"Hello",
    course: "<b>Vue<b>",
    headingId:"heading",
    isDisabled:true,
    status:"danger",
    isPromoted:true,
    isSoldout:false,
    highlightColor:'orange',
    headerSize: 50,
    headerStyleObject:{
      color: "orange",
      fontSize:'50px',
      
    }

  };
},

};
</script>


<style>
.underline{
  text-decoration: underline;
}

.promoted{
  font-style:italic ;
}

.new{
  color: green;
}

.soldout{
  color: red;
}
</style>
