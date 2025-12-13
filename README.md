<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>KD | TOTY</title>

<style>
body {
    background: url("https://github.com/konnidex/konnidex-toty/blob/main/images/webbackground.PNG?raw=true") no-repeat center center fixed;
    background-size: cover;
    font-family: Arial, sans-serif;
    text-align: center;
    padding: 20px;
}


.formation {
    width: 600px;
    margin: auto;
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-template-rows: repeat(4, 120px);
    gap: 15px;
    color:#d4c369;
}

.box {
    width: 110px;
    height: 110px;
    background: #0e3460;
    border: 2px solid #d4c369;
    display: flex;
    justify-content: center;
    align-items: center;
}

.box img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 8px;
}

#LW { grid-column: 1; grid-row: 1; }
#ST { grid-column: 3; grid-row: 1; }
#RW { grid-column: 5; grid-row: 1; }

#CM1 { grid-column: 2; grid-row: 2; }
#CM2 { grid-column: 3; grid-row: 2; }
#CM3 { grid-column: 4; grid-row: 2; }

#LB { grid-column: 1; grid-row: 3; }
#CB1 { grid-column: 2; grid-row: 3; }
#CB2 { grid-column: 4; grid-row: 3; }
#RB { grid-column: 5; grid-row: 3; }

#GK { grid-column: 3; grid-row: 4; }

.tabs {
    margin-top: 40px;
    display: flex;
    justify-content: center;
    gap: 8px;         /* smaller gap so they fit on mobile */
    flex-wrap: nowrap; /* keep them in ONE row */
}

.tabs button {
    padding: 8px 15px;   /* smaller padding for mobile */
    font-size: 15px;     /* slightly smaller text */
    cursor: pointer;
    border: none;
    background: #0e3460;
    color: #d4c369;
    border-radius: 5px;
    white-space: nowrap; /* forces text to stay on one line */
}


.tabs button.active {
    background: #0d47a1;
}

.slider-container {
    margin-top: 40px;
    width: 100%;
    overflow-x: auto;
    white-space: nowrap;
    padding: 30px;
    touch-action: none;      
    pointer-events: auto;
}

.player-img {
    width: 90px;
    height: 90px;
    object-fit: cover;
    cursor: grab;
    margin: 5px;
    display: inline-block;
}
@media (max-width: 600px) {
    /* Center the tabs */
    .tabs {
        justify-content: center; /* already center, just to be sure */
        margin: 20px auto;       /* add auto horizontal margin */
        width: 100%;
        padding: 0 10px;         /* small side padding */
        box-sizing: border-box;
    }

    /* Center the slider container */
    .slider-container {
        display: flex;
        justify-content: center; /* center the player images */
        overflow: hidden;
        width: 150%;
        padding: 0 10px;         /* small side padding */
        box-sizing: border-box;
    }

    /* Ensure player images stay inline-block */
    .player-img {
        display: inline-block;
        margin: 5px;
    }
}
.slider-container button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    z-index: 10;
}

.slider-container button:first-child { left: 0; }
.slider-container button:last-child { right: 0; }

#playerSlider {
  display: flex;
  gap: 12px;
  overflow-x: auto;              /* make scrollable */
  overflow-y: hidden;
  -webkit-overflow-scrolling: touch; /* momentum scrolling on iOS */
  scroll-behavior: smooth;
  touch-action: pan-x;           /* allow horizontal swipe even on children */
  cursor: grab;
}

#playerSlider:active {
  cursor: grabbing;
}

/* Optional scrollbar styling (visible on Android / PC) */
#playerSlider::-webkit-scrollbar {
  height: 8px;
}
#playerSlider::-webkit-scrollbar-thumb {
  background: #d4c369;
  border-radius: 10px;
}
#playerSlider::-webkit-scrollbar-track {
  background: rgba(255,255,255,0.15);
}



</style>
</head>
<body>
<div class="formation">
    <div class="box" id="LW" data-type="attackers">ATT</div>
    <div class="box" id="ST" data-type="attackers">ATT</div>
    <div class="box" id="RW" data-type="attackers">ATT</div>

    <div class="box" id="CM1" data-type="midfielders">MID</div>
    <div class="box" id="CM2" data-type="midfielders">MID</div>
    <div class="box" id="CM3" data-type="midfielders">MID</div>

    <div class="box" id="LB" data-type="defenders">DEF</div>
    <div class="box" id="CB1" data-type="defenders">DEF</div>
    <div class="box" id="CB2" data-type="defenders">DEF</div>
    <div class="box" id="RB" data-type="defenders">DEF</div>

    <div class="box" id="GK" data-type="keepers">GK</div>

</div>

<div class="tabs">
    <button class="tab-btn active" data-type="attackers">Attackers</button>
    <button class="tab-btn" data-type="midfielders">Midfielders</button>
    <button class="tab-btn" data-type="defenders">Defenders</button>
    <button class="tab-btn" data-type="keepers">Goalkeepers</button>
</div>

<div class="slider-container" id="playerSlider">
    <!-- Attackers -->
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/dembele.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/kavara.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/doue.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/raphinia.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/osimhen.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/olise.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/mbappe.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/lewa.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/lautaro.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/kane.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/haaland.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/gyokres.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/guirassy.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/yamal.png?raw=true">
    <img draggable="true" class="player-img attackers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/salah.png?raw=true">
    <!-- Midfielders -->
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/barella.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/bruno.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/caicedo.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/coldpalmer.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/enzofernandez.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/fabianruiz.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/pedri.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/gravenchberg.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/macallister.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/mctominiy.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/neves.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/rice.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/vitiniha.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/joshua.png?raw=true">
    <img draggable="true" class="player-img midfielders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/jude.png?raw=true">

    <!-- Defenders -->
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/15.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/23.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/cubarsi.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/cucrella.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/dimarco.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/dumfries.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/gabriel.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/konate.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/kounde.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/upamecano.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/marquihnihos.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/pacho.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/rudiger.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/tah.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/saliba.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/virgilvandijk.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/bastoni.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/inigo.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/nunomendes.png?raw=true">
    <img draggable="true" class="player-img defenders" src="https://github.com/konnidex/konnidex-toty/blob/main/images/cristianromero.png?raw=true">

    <!-- Keepers -->
    <img draggable="true" class="player-img keepers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/courtious.png?raw=true">
    <img draggable="true" class="player-img keepers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/alisson.png?raw=true">
    <img draggable="true" class="player-img keepers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/oblak.png?raw=true">
    <img draggable="true" class="player-img keepers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/raya.png?raw=true">
    <img draggable="true" class="player-img keepers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/sels.png?raw=true">
    <img draggable="true" class="player-img keepers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/donna.png?raw=true">
    <img draggable="true" class="player-img keepers" src="https://github.com/konnidex/konnidex-toty/blob/main/images/sommer.png?raw=true">

</div>

<p style="
    color: #d4c369;
    font-size: 18px;
">
    *Swipe the visible slider , add players <br>take screenshot and submit vote.
</p>

<a style="
background:#0e3460;
color:#d4c369;
right:243px;
font-size:20px;
padding:12px 22px;
border-radius:12px;
text-decoration:none;
font-weight:600;
box-shadow:0 4px 10px rgba(0,0,0,0.3);
" 
class="btn btn-primary" 
href="https://tally.so/r/KYpldK" 
target="_blank" 
rel="noopener noreferrer">
Submit
</a>

<script>
let draggedPlayer = null;
let draggedFromBox = null;
let touchClone = null;
let currentTouchBox = null;

const slider = document.getElementById("playerSlider");
const boxes = document.querySelectorAll(".box");

// ---------------- DESKTOP DRAG -----------------
document.addEventListener("dragstart", e => {
    if (e.target.classList.contains("player-img")) {
        draggedPlayer = e.target;
        draggedFromBox = draggedPlayer.parentElement.classList.contains("box")
            ? draggedPlayer.parentElement
            : null;
    }
});

boxes.forEach(box => {
    box.addEventListener("dragover", e => e.preventDefault());
    box.addEventListener("drop", () => dropIntoBox(box));
});

slider.addEventListener("dragover", e => e.preventDefault());
slider.addEventListener("drop", () => dropToSlider());

// ---------------- TOUCH DRAG (MOBILE) -----------------
document.querySelectorAll(".player-img").forEach(img => {
    img.addEventListener("touchstart", e => {
        draggedPlayer = img;
        draggedFromBox = img.parentElement.classList.contains("box") 
            ? img.parentElement 
            : null;

        touchClone = img.cloneNode(true);
        touchClone.style.position = "fixed";
        touchClone.style.width = img.offsetWidth + "px";
        touchClone.style.height = img.offsetHeight + "px";
        touchClone.style.pointerEvents = "none";
        touchClone.style.opacity = "0.8";

        document.body.appendChild(touchClone);
    });

    img.addEventListener("touchmove", e => {
        if (!draggedPlayer) return; // allow normal slider scroll

        let t = e.touches[0];
        touchClone.style.left = t.clientX - 45 + "px";
        touchClone.style.top = t.clientY - 45 + "px";

        currentTouchBox = [...boxes].find(b => {
            let rect = b.getBoundingClientRect();
            return (
                t.clientX > rect.left &&
                t.clientX < rect.right &&
                t.clientY > rect.top &&
                t.clientY < rect.bottom
            );
        });

        e.preventDefault(); // only prevent scroll when dragging player
    });

    img.addEventListener("touchend", () => {
        if (currentTouchBox) {
            dropIntoBox(currentTouchBox);
        } else {
            dropToSlider();
        }

        if (touchClone) touchClone.remove();
        touchClone = null;
        draggedPlayer = null;
        draggedFromBox = null;
    });
});

// --------------- DROP INTO BOX ----------------
function dropIntoBox(box) {
    if (!draggedPlayer) return;

    let required = box.dataset.type;
    let type = [...draggedPlayer.classList].find(c =>
        ["attackers", "midfielders", "defenders", "keepers"].includes(c)
    );

    if (required !== type) {
        draggedPlayer = null;
        draggedFromBox = null;
        return;
    }

    if (box.children.length > 0) {
        let existing = box.children[0];
        if (draggedFromBox) {
            draggedFromBox.appendChild(existing);
        } else {
            slider.appendChild(existing);
        }
    }

    box.innerHTML = "";
    box.appendChild(draggedPlayer);

    draggedPlayer = null;
    draggedFromBox = null;
}

// --------------- DROP BACK TO SLIDER --------------
function dropToSlider() {
    if (!draggedPlayer) return;
    slider.appendChild(draggedPlayer);
    draggedPlayer = null;
    draggedFromBox = null;
}

// ---------------- CATEGORY FILTER ----------------
document.querySelectorAll(".tab-btn").forEach(btn => {
    btn.addEventListener("click", () => {
        document.querySelectorAll(".tab-btn").forEach(b => b.classList.remove("active"));
        btn.classList.add("active");

        let type = btn.dataset.type;

        slider.querySelectorAll(".player-img").forEach(img => {
            if (img.parentElement.classList.contains("box")) return;
            img.style.display = img.classList.contains(type) ? "inline-block" : "none";
        });
    });
});

// ---------------- DEFAULT CATEGORY ----------------
window.onload = () => {
    let defaultType = "attackers";

    slider.querySelectorAll(".player-img").forEach(img => {
        if (!img.parentElement.classList.contains("box")) {
            img.style.display = img.classList.contains(defaultType) ? "inline-block" : "none";
        }
    });
};

let isDraggingSlider = false;
let startX = 0;
let scrollLeft = 0;

slider.addEventListener("pointerdown", e => {
  if (e.target.classList.contains("player-img")) return;

  isDraggingSlider = true;
  startX = e.clientX;
  scrollLeft = slider.scrollLeft;

  // temporarily disable selection and pointer events on players
  slider.querySelectorAll(".player-img").forEach(img => {
    img.style.userSelect = "none";
    img.style.pointerEvents = "none";
  });

  slider.style.cursor = "grabbing";
});

slider.addEventListener("pointermove", e => {
  if (!isDraggingSlider) return;
  const dx = e.clientX - startX;
  slider.scrollLeft = scrollLeft - dx;
});

const stopSliderDrag = () => {
  if (!isDraggingSlider) return;
  isDraggingSlider = false;

  slider.querySelectorAll(".player-img").forEach(img => {
    img.style.userSelect = "";
    img.style.pointerEvents = "";
  });

  slider.style.cursor = "grab";
};

slider.addEventListener("pointerup", stopSliderDrag);
slider.addEventListener("pointercancel", stopSliderDrag);
slider.addEventListener("pointerleave", stopSliderDrag);


</script>






</body>
</html>
