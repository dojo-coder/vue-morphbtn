<template>
  <div :class="{ 'morph-button morph-button-overlay morph-button-fixed' : true, 'open': isOpened, 'no-transition' : noTran, 'active': isActive }">
    <button ref="button" @click="this.toggle" type="button">Start your project now</button>
    <div class="morph-content" ref="content" :style="{ 'left': contentLeft, 'top': contentTop }">
      <div>
        <div class="content-style-overlay">
          <span class="icon icon-close" @click="this.toggle">Close the overlay</span>
          <h2>About Parsley</h2>
          <p>Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.</p>
          <p>Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter purslane kale. Celery potato scallion desert raisin horseradish spinach carrot soko. Lotus root water spinach fennel kombu maize bamboo shoot green bean swiss chard seakale pumpkin onion chickpea gram corn pea. Brussels sprout coriander water chestnut gourd swiss chard wakame kohlrabi beetroot carrot watercress. Corn amaranth salsify bunya nuts nori azuki bean chickweed potato bell pepper artichoke.</p>
          <p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.</font></font></p>
          <p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter purslane kale. Celery potato scallion desert raisin horseradish spinach carrot soko. Lotus root water spinach fennel kombu maize bamboo shoot green bean swiss chard seakale pumpkin onion chickpea gram corn pea. Brussels sprout coriander water chestnut gourd swiss chard wakame kohlrabi beetroot carrot watercress. Corn amaranth salsify bunya nuts nori azuki bean chickweed potato bell pepper artichoke.</font></font></p>
          <p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.</font></font></p>
          <p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Turnip greens yarrow ricebean rutabaga endive cauliflower sea lettuce kohlrabi amaranth water spinach avocado daikon napa cabbage asparagus winter purslane kale. Celery potato scallion desert raisin horseradish spinach carrot soko. Lotus root water spinach fennel kombu maize bamboo shoot green bean swiss chard seakale pumpkin onion chickpea gram corn pea. Brussels sprout coriander water chestnut gourd swiss chard wakame kohlrabi beetroot carrot watercress. Corn amaranth salsify bunya nuts nori azuki bean chickweed potato bell pepper artichoke.</font></font></p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      isAnimating: false,
      noTran: false,
      contentTop: '0px',
      contentLeft: '0px',
      isActive: false,
      isOpened: false
    }
  },
  methods:{
    toggle(){
      if( this.isAnimating ) return false;

        
// console.log('test');
        // set the left and top values of the contentEl (same like the button)
        var buttonPos = this.$refs.button.getBoundingClientRect();
        // need to reset
        // classie.addClass( this.contentEl, 'no-transition' );
        this.noTran = true;
        this.contentLeft = 'auto';
        this.contentTop = 'auto';
        this.isActive = !this.isActive;
        var self = this;
        self.isAnimating = !self.isAnimating;  
        setTimeout( () => { 
          self.contentLeft = buttonPos.left + 'px';
          self.contentTop = buttonPos.top + 'px';
          setTimeout( () => {
              
              self.isOpened = !self.isOpened;    
              self.isAnimating = !self.isAnimating;      
          },25);
        },25);
    }
  }
}
</script>

<style scoped>
.morph-button-fixed, .morph-button-fixed .morph-content{
  width: 300px;
    height: 300px;
    border-radius: 300px;
    display: block;
    overflow: hidden;
}

.morph-button {
    position: relative;
    display: block;
    margin: 0 auto;
}
.morph-button.morph-button-overlay {
    margin: 50px auto;
}
.morph-button-fixed > button {
    z-index: 1000;
    width: 100%;
    height: 100%;
    -webkit-transition: opacity 0.1s 0.5s;
    transition: opacity 0.1s 0.5s;
}
.morph-button > button {
    position: relative;
    padding: 0 1em;
    border: none;
    background-color: #e85657;
    color: #f9f6e5;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: 700;
    line-height: 80px;
    overflow: hidden;
}

p{
  margin: 50px;
}
.icon{
  margin: 40px;
}
.morph-button .morph-content, .morph-button.open .morph-content, .morph-button-modal-4 .morph-clone{
  transition-timing-function: cubic-bezier(0.7,0,0.3,1);
}
.morph-button-overlay .morph-content {
    overflow: hidden;
    background: #e85657;
}
.morph-button-overlay .morph-content, .morph-button-sidebar .morph-content {
    -webkit-transition: opacity 0.3s 0.5s, width 0.4s 0.1s, height 0.4s 0.1s, top 0.4s 0.1s, left 0.4s 0.1s, border-radius 0.4s 0.1s;
    transition: opacity 0.3s 0.5s, width 0.4s 0.1s, height 0.4s 0.1s, top 0.4s 0.1s, left 0.4s 0.1s, border-radius 0.4s 0.1s;
}
.morph-button-fixed .morph-content {
    position: fixed;
    z-index: 900;
    opacity: 0;
    -webkit-transition: opacity 0.3s 0.5s, width 0.4s 0.1s, height 0.4s 0.1s, top 0.4s 0.1s, left 0.4s 0.1s, margin 0.4s 0.1s;
    transition: opacity 0.3s 0.5s, width 0.4s 0.1s, height 0.4s 0.1s, top 0.4s 0.1s, left 0.4s 0.1s, margin 0.4s 0.1s;
}
.morph-content {
    pointer-events: none;
}

.morph-button-fixed.active .morph-content {
    z-index: 1900;
}


.morph-button-overlay.open .morph-content {
    top: 0 !important;
    left: 0 !important;
    width: 100%;
    height: 100%;
}
.morph-button-overlay.open .morph-content {
    border-radius: 0px;
}
.morph-button-fixed.active .morph-content {
    z-index: 1900;
}
.morph-button-fixed.open .morph-content {
    opacity: 1;
}
.morph-button.open .morph-content {
    pointer-events: auto;
}
.morph-button-overlay.open .morph-content, .morph-button-sidebar.open .morph-content{
  transition: width 0.4s 0.1s, height 0.4s 0.1s, top 0.4s 0.1s, left 0.4s 0.1s, border-radius 0.4s 0.1s;
}
.morph-button-fixed.active .morph-content {
    z-index: 1900;
}
</style>
