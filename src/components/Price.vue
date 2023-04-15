<template>
    <div class="between">
      <div class="head2">{{ selectedText[0] }} PAGEVIEWS</div>
      <div class="head2">
        <span class="price">$</span>
        <span v-if="discount" class="price">{{ selectedText[2] }}</span>
        <span v-else class="price">{{ selectedText[1] }}</span>
        /month
      </div> 
    </div>
    <input type="range" min="0" max="4" v-model="selectedValue" id="slider" @input="onSliderChange">
    <div class="toggleContainer">
      <div>Monthly Billing</div>
      <div>
        <label class="switch">
          <input type="checkbox" v-model="discount">
          <span class="sliderToggle"></span>
        </label>
      </div>
      <div>
        Yearly Billing
        <span class="red">25% discount</span>
      </div>
    </div>
    <div class="gap">
        <p v-show='showRed'>Hooray! you have applied 25% discount.</p>
    </div>
  </template>
  
  <script setup>
  import { ref, watchEffect } from 'vue'
  
  let selectedValue = 0;
  let selectedText = ref(['10K', 8, 8*0.75]);
  
  const priceRange = ref([
    ['10K', 8],
    ['50K', 12],
    ['100K', 16],
    ['500K', 24],
    ['1M', 36]
  ]);
  
  // declare new value of discounted price
  for (let i = 0; i < priceRange.value.length; i++) {   
    priceRange.value[i][2] = priceRange.value[i][1] * 0.75;
  }
  
  function onSliderChange(event) {
    const stepCount = parseInt(event.target.value);
    selectedText.value = [priceRange.value[stepCount][0], 
    priceRange.value[stepCount][1], priceRange.value[stepCount][2]
    ];
  }
  
    let discount = ref(false);
    let showRed = ref(false);

    watchEffect(() => {
    if (discount.value) {
        showRed.value = true;
    } else {
        showRed.value = false;
    }
    });
</script>
  