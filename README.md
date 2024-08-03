## PIYUSH SHARMA

<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>
<div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div><div class="cell"></div>

<div class="scene">

  <div class="sign">
    <div class="shadow"></div>
    <div class="sign_front"></div>
    <div class="sign_topIn"></div>
    <div class="sign_topOut"></div>
    <div class="sign_bottomIn"></div>
    <div class="sign_bottomOut"></div>
    <div class="sign_leftIn"></div>
    <div class="sign_leftOut"></div>
    <div class="sign_rightIn"></div>
    <div class="sign_rightOut"></div>

    <div class="sign_segments">
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
      <div class="sign_segment"><div></div><div></div><div></div></div>
    </div>
  </div>
</div>
@import url('https://fonts.googleapis.com/css2?family=Berkshire+Swash&display=swap');

*, *::before, *::after {
    padding: 0;
    margin: 0 auto;
    box-sizing: border-box;
}

:root {
    --boxSize: 1em;
    --speed: 18s;
    --rotateSceneX: -0deg; 
    --rotateSceneY: 0deg; 
}

$signColor: #544;

body {
    font-family: 'Berkshire Swash', cursive;
    background-color: #aaa;
    height: 100vh;
    display: grid;
    grid-template-columns: repeat(10, 1fr);
    grid-template-rows: repeat(10, 1fr);
    perspective: 100em;
    overflow: hidden;
}

.cell {
    width: 100%; height: 100%;

    @for $i from 0 to 10 {
        &:nth-child(10n + #{$i + 1}):hover ~ .scene {
            --rotateSceneY: #{-63 + ($i * 14)}deg;
        }
        &:nth-child(n + #{10 * $i + 1}):nth-child(-n + #{10 * ($i + 1)}):hover ~ .scene {
            --rotateSceneX: #{36 - ($i * 8)}deg;
        }
    }
}

.scene {
    position: fixed;
    top: 50%; left: 50%;
    transform-style: preserve-3d;
    transform: translateZ(-0em) rotateX(var(--rotateSceneX)) rotateY(var(--rotateSceneY));
    transition: transform 0.5s;
    z-index: -1;
}

.sign {
    position: absolute;
    top: -14.25em; left: -26em;
    width: 52em; height: 28.5em;
    background-color: darken($signColor, 30%);
    transform-style: preserve-3d;

    &_front {
        width: 100%; height: 100%;
        transform: translateZ(2em);
        background-image:
            linear-gradient(0deg,   $signColor 2em, transparent 2em),
            linear-gradient(90deg,  $signColor 2em, transparent 2em),
            linear-gradient(180deg, $signColor 2em, transparent 2em),
            linear-gradient(270deg, $signColor 2em, transparent 2em)
        ;
    }

    &_topIn, &_topOut {
        position: absolute;
        height: 2em;
        background-color: lighten($signColor, 5%);
        transform-origin: top;
        transform: rotateX(90deg);
    }
    &_topIn {
        bottom: 0; left: 2em;
        width: calc(100% - 4em);
    }
    &_topOut {
        top: 0; left: 0;
        width: 100%;
    }
    
    &_bottomIn, &_bottomOut {
        position: absolute;
        height: 2em;
        background-color: darken($signColor, 15%);
        transform-origin: bottom;
        transform: rotateX(-90deg);
    }
    &_bottomIn {
        top: 0; left: 2em;
        width: calc(100% - 4em);
    }
    &_bottomOut {
        bottom: 0; left: 0;
        width: 100%;
    }
    
    &_leftIn, &_leftOut {
        position: absolute;
        width: 2em;
        background-color: darken($signColor, 5%);
        transform-origin: left;
        transform: rotateY(-90deg);
    }
    &_leftIn {
        top: 2em; right: 0;
        height: calc(100% - 4em);
    }
    &_leftOut {
        top: 0; left: 0;
        height: 100%;
    }

    &_rightIn, &_rightOut {
        position: absolute;
        width: 2em;
        background-color: darken($signColor, 10%);
        transform-origin: right;
        transform: rotateY(90deg);
    }
    &_rightIn {
        top: 2em; left: 0;
        height: calc(100% - 4em);
    }
    &_rightOut {
        top: 0; right: 0;
        height: 100%;
    }

    &_segment {
        position: absolute;
        top: 2em;
        width: 2em; height: 24.5em; 
        transform: translateX(-50%) translateZ(1em);
        transform-style: preserve-3d;

        @for $p from 0 to 24 {
            &:nth-child(#{$p + 1}) {
                left: #{3 + ($p * 2)}em;
                --ad: #{$p};
            }
        }

        &::before {
            content: '';
            position: absolute;
            top: 0; left: 0.5em;
            width: 1em; height: 100%;
            background-image: linear-gradient(90deg,  #333, #aaa, #333);
            transform: rotateY(calc(var(--rotateSceneY) * -1));
        }

        & > div {
            position: absolute;
            top: 0.25em; left: 0.05em;
            width: 1.9em; height: 24em;
            animation: signflip var(--speed) cubic-bezier(.5,0,.7,1.5) infinite;
            overflow: hidden;
            background-position: calc(var(--ad) / 23 * 100%) 50%;
            background-size: 48em 24em;
            text-align: center;

            @for $i from 0 to 3 {
                &:nth-child(#{$i + 1}) {
                    background-image: url('https://assets.codepen.io/1948355/trivision#{$i + 1}.jpg');
                    animation-delay: calc((var(--speed) * #{$i / -3}) - var(--speed) + (var(--ad) * 0.1s));
                    box-shadow: 0 0 1em #0007 inset;

                    &::after {
                        background-image: inherit;
                    }
                }
            }
            
            $d: 0.53em;
            @keyframes signflip {
                0%, 26.666% { transform: rotateY(0deg) translateZ(#{$d}); }
                33.333%, 60% { transform: rotateY(120deg) translateZ(#{$d}); }
                66.666%, 93.333% { transform: rotateY(240deg) translateZ(#{$d}); }
                100% { transform: rotateY(360deg) translateZ(#{$d}); }
            }

            &:nth-child(1)::after {
                content: "DREAM";
                position: absolute;
                top: 0; left: calc(var(--ad) * -0.2em);
                font-size: 10em;
                width: 4.8em; height: 2.4em;
                padding-top: 0.6em;
                background-size: 4.8em 2.4em;
                filter: drop-shadow(0 0 0.1em #fff) drop-shadow(0 0 0.5em #00f);
                background-clip: text;
                -webkit-background-clip: text;
                color: transparent;
            }

            &:nth-child(2)::after {
                content: "LOVE";
                position: absolute;
                top: 0.8em; left: calc(var(--ad) * -0.2em);
                font-size: 10em;
                width: 3.4em;
                filter: drop-shadow(0 0 0.1em #000);
                background-size: 5.2em 2.6em;
                background-position: right top;
                background-clip: text;
                -webkit-background-clip: text;
                color: transparent;
            }

            &:nth-child(3)::after {
                content: "HOPE";
                position: absolute;
                top: 0; left: calc(var(--ad) * -0.25em);
                font-size: 8em;
                width: 6em; height: 3em;
                padding: 1.5em 0 0 2.1em;
                background-image: url('https://assets.codepen.io/1948355/trivision4.jpg');
                background-size: 100%;
                filter: drop-shadow(-0.025em 0.025em 0.05em #fff);
                background-clip: text;
                -webkit-background-clip: text;
                color: transparent;
            }
        }
    }
}

.shadow {
    position: fixed;
    top: 50%; left: 50%;
    width: 65em; height: 36em;
    transform: translate(-50%, -50%) translateZ(-20em);
    background-color: #0003;
    filter: blur(3em);
}

<img src="https://hashincludepiyush.github.io/IMG_20240711_180649155.jpg" style="display: block; margin: auto; width: 100%; height: 100%;"/>

[Ph. D. Thesis, 2024](https://drive.google.com/file/d/13iQh358T0XyYqrT-jJAwYLekEkHou_2F/view?usp=drivesdk)

[TRANSFORMING THE INDIAN POWER SECTOR Distribution System Operators (DSOs): Need, Frameworks, and Regulatory Considerations. Government of India, 2023](https://iusstf.org/documents/35627/42091/Whitepaper%20Transforming%20the%20Indian%20Power%20Sector)
      
[A novel interior-exterior approach for the TSO-DSO based bilevel optimal power flow. IEEE Transactions on Power Systems, 2023](https://ieeexplore.ieee.org/abstract/document/10192376)

[Real time adjustment to mitigate the SPV forecasting errors with BESS and EV - an utility case study. 2022 IEEE 10th Power India International Conference (PIICON), National Institute of Technology Delhi, Delhi, 2022](https://ieeexplore.ieee.org/abstract/document/10045243)

[Power circle diagrams and aggregate flexibility curves for active distribution networks. Electric Power Systems Research, 2022](https://www.sciencedirect.com/science/article/abs/pii/S0378779622000505)

[CER MONOGRAPH Regulatory Framework for Long-Term Demand Forecasting and Power Procurement Planning. Centre for Energy Regulation, Indian Institute of Technology Kanpur, Uttar Pradesh, 2019](https://cer.iitk.ac.in/assets/downloads/CER_Monograph.pdf)

[Investigation of network reconfiguration on the reliability and performance of distribution systems using CRO. 2017 6th International Conference on Computer Applications In Electrical Engineering Recent Advances (CERA), Indian Institute of Technology Roorkee, Uttarakhand, 2017](https://ieeexplore.ieee.org/document/8343305)
