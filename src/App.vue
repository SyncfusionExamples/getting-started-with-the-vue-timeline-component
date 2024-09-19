<script setup>
  import { TimelineComponent, 
    ItemDirective as Item,
    ItemsDirective as Items
   } from '@syncfusion/ej2-vue-layouts';
</script>
<template>
  <div class="timeline-component">
    <TimelineComponent align="Alternate" orientation="Horizontal">
      <Items>
        <Item :content="'ordered'" oppositeContent="9:15 AM, January 1, 2024"
        dotCss="state-success" cssClass="completed"></Item>
        <template v-slot:ordered>
          <div class="timeline-content">
            <p>Order was placed successfully.</p>
            <p>Details: USB Wired-Mouse, Quantity: 3</p>
          </div>
        </template>
        <Item :content="'shipped'" oppositeContent="12:20 PM, January 4, 2024"
        dotCss="state-success" cssClass="completed"></Item>
        <template v-slot:shipped>
          <div class="timeline-content">
            <p>Order has been shipped.</p>
            <p>Tracking Number: 123456789</p>
          </div>
        </template>
        <Item content="Out for Delivery" oppositeContent="07:00 AM, January 8, 2024"
        dotCss="state-progress" cssClass="intermediate"></Item>
        <Item content="Delivered" oppositeContent="Estimated delivery by 09:20 AM"
        :disabled="true"></Item>
      </Items>
    </TimelineComponent>
  </div>
</template>
<style>
  @import '../node_modules/@syncfusion/ej2-base/styles/material.css';
  @import '../node_modules/@syncfusion/ej2-vue-layouts/styles/material.css';
  .timeline-component {
    height: 350px;
    width: 520px;
    margin: 10% auto;
    position: relative;
    /* .state-progress{
      outline-color: #007bff;
      background-color: #007bff;
      --dot-size: 25px;
    }
    .state-success{
      outline-color: #28a745;
      background-color: #28a745;
    }
    .completed.e-connector::after {
      border-color:#28a745;
    }
    .intermediate.e-connector::after {
      border-style: dashed;
    } */
  }
  .template-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 0;
    position: relative;
  }
  .content-container {
    width: 80%;
  }
  .timeline-content {
    padding: 10px;
    border-radius: 5px;
    background-color: #f1f1f1;
    font-family: Arial, sans-serif;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  }
  .content-connector {
    position: absolute;
    height: 2px;
    width: 100%;
    background-color: #ccc;
    top: 50%;
    left: 10%;
    z-index: 1;
  }
  .progress-line {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    position: relative;
    width: 25px;
  }
  .indicator {
    width: var(--dot-size, 20px);
    height: var(--dot-size, 20px);
    border-radius: 50%;
    background-color: #ccc;
    position: relative;
    z-index: 2;
  }
</style>
