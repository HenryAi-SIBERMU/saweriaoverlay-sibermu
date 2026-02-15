# Konfigurasi Saweria

Salin kode di bawah ini ke pengaturan Overlay Saweria Anda.

## HTML
Silakan copy kode ini ke kolom **HTML**:

```html
<div class="alert">
  <p class="template">
    <span class="donatur">{donator}</span> mendukung sejumlah
    <span class="amount">{amount}</span>
  </p>
  <p class="message">{message}</p>
</div>
```

## CSS
Silakan copy kode ini ke kolom **CSS**.


```css
.alert {
  position: relative;
  /* Background image template */
  /* Background image template */
  background-image: url('https://i.imgur.com/BFtF7Qf.png');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;

  /* Adjust dimensions to match the image aspect ratio */
  width: 850px;
  height: 300px;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  /* Padding adjustments to avoid overlapping the person image */
  padding: 20px;
  padding-right: 240px; 
  box-sizing: border-box;

  text-align: center;
  font-family: "IBM Plex Mono", monospace;
  font-size: 2em; /* Font size increased */
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
  text-size-adjust: 100%;
  text-rendering: optimizelegibility;
  color: #ffffff;

  border-radius: 10px;
}

/* Animated Border (Stroke Box) */
.alert:after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  border-radius: 10px;
  /* Gradient SiberMu Blue & Gold */
  background: linear-gradient(120deg, #003366, #00aaff, #ffd700);
  background-size: 300% 300%;
  pointer-events: none;
  z-index: 1;
  
  clip-path: polygon(0% 100%,
          10px 100%,
          10px 10px,
          calc(100% - 10px) 10px,
          calc(100% - 10px) calc(100% - 10px),
          10px calc(100% - 10px),
          10px 100%,
          100% 100%,
          100% 0%,
          0% 0%);
}

.alert.in:after {
  animation: frame-enter 1s forwards ease-in-out reverse, gradient-animation 4s ease-in-out infinite;
}

/* motion */
@keyframes gradient-animation {
  0% {
      background-position: 15% 0%;
  }
  50% {
      background-position: 85% 100%;
  }
  100% {
      background-position: 15% 0%;
  }
}

@keyframes frame-enter {
  0% {
      clip-path: polygon(0% 100%, 10px 100%, 10px 10px, calc(100% - 10px) 10px, calc(100% - 10px) calc(100% - 10px), 10px calc(100% - 10px), 10px 100%, 100% 100%, 100% 0%, 0% 0%);
  }
  25% {
      clip-path: polygon(0% 100%, 10px 100%, 10px 10px, calc(100% - 10px) 10px, calc(100% - 10px) calc(100% - 10px), calc(100% - 10px) calc(100% - 10px), calc(100% - 10px) 100%, 100% 100%, 100% 0%, 0% 0%);
  }
  50% {
      clip-path: polygon(0% 100%, 10px 100%, 10px 10px, calc(100% - 10px) 10px, calc(100% - 10px) 10px, calc(100% - 10px) 10px, calc(100% - 10px) 10px, calc(100% - 10px) 10px, 100% 0%, 0% 0%);
  }
  75% {
      -webkit-clip-path: polygon(0% 100%, 10px 100%, 10px 10px, 10px 10px, 10px 10px, 10px 10px, 10px 10px, 10px 10px, 10px 0%, 0% 0%);
  }
  100% {
      -webkit-clip-path: polygon(0% 100%, 10px 100%, 10px 100%, 10px 100%, 10px 100%, 10px 100%, 10px 100%, 10px 100%, 10px 100%, 0% 100%);
  }
}

.message {
  font-weight: bolder;
  margin-top: 10px;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
  z-index: 10;
  position: relative;
}

.template {
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
  margin: 0;
  z-index: 10;
  position: relative;
}

.donatur,
.amount {
  color: #ff8b75;
  font-weight: bold;
}

/* Entrance Animation */
.alert.in {
  animation: bounceIn 0.8s cubic-bezier(0.215, 0.610, 0.355, 1.000) both;
}

@keyframes bounceIn {
  0% {
      opacity: 0;
      transform: scale3d(.3, .3, .3);
  }
  20% {
      transform: scale3d(1.1, 1.1, 1.1);
  }
  40% {
      transform: scale3d(.9, .9, .9);
  }
  60% {
      opacity: 1;
      transform: scale3d(1.03, 1.03, 1.03);
  }
  80% {
      transform: scale3d(.97, .97, .97);
  }
  100% {
      opacity: 1;
      transform: scale3d(1, 1, 1);
  }
}

/* Wiggle Animation */
.alert:hover {
  animation: wiggle 0.5s ease-in-out;
}

@keyframes wiggle {
  0% { transform: rotate(0deg); }
  25% { transform: rotate(2deg); }
  50% { transform: rotate(-2deg); }
  75% { transform: rotate(1deg); }
  100% { transform: rotate(0deg); }
}
```
