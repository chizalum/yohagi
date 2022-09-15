<template>
    <div class="lds-spinner">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>
  </template>
  
  <script>
  export default {
      name: "spinner",
  };
  </script>
  
  <style>
  .lds-spinner {
    color: official;
    display: inline-block;
    position: relative;
    width: 80px;
    height: 80px;
  }
  .lds-spinner div {
    transform-origin: 40px 22px;
    animation: lds-spinner 0.7s linear infinite;
  }
  .lds-spinner div:after {
    content: " ";
    display: block;
    position: absolute;
    top: 3px;
    left: 37px;
    width: 6px;
    height: 12px;
    border-radius: 20%;
    background: black;
  }
  .lds-spinner div:nth-child(1) {
    transform: rotate(15deg);
    animation-delay: -0.7s;
  }
  .lds-spinner div:nth-child(2) {
    transform: rotate(60deg);
    animation-delay: -0.6s;
  }
  .lds-spinner div:nth-child(3) {
    transform: rotate(105deg);
    animation-delay: -0.5s;
  }
  .lds-spinner div:nth-child(4) {
    transform: rotate(150deg);
    animation-delay: -0.4s;
  }
  .lds-spinner div:nth-child(5) {
    transform: rotate(195deg);
    animation-delay: -0.3s;
  }
  .lds-spinner div:nth-child(6) {
    transform: rotate(240deg);
    animation-delay: -0.2s;
  }
  .lds-spinner div:nth-child(7) {
    transform: rotate(285deg);
    animation-delay: -0.1s;
  }
  .lds-spinner div:nth-child(8) {
    transform: rotate(330deg);
    animation-delay: 0s;
  }
  @keyframes lds-spinner {
    0% {
      opacity: 1;
    }
    100% {
      opacity: 0;
    }
  }
  </style>