# CellsandIntroductiontoPlantsandAnimals
Review for the upcoming test
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<title>Endodragon Quest</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Silkscreen:wght@400;700&family=Nunito:wght@500;700;800&display=swap">
<style>
/* Layout: one dark "night arcade" page. Title band, 16:9 game screen, then help and teacher notes stacked below. */
:root{
  --bg:#12101f; --panel:#1d1a33; --line:#38325e; --fg:#f2eefc; --muted:#b4acd6;
  --glow:#ffd75e; --glow2:#6ef0ff; --good:#7ce38b; --bad:#ff8a7a;
  --display:"Silkscreen","Courier New",monospace;
  --body:"Nunito","Trebuchet MS",system-ui,sans-serif;
  color-scheme:dark;
}
[hidden]{display:none!important}
*,*::before,*::after{box-sizing:border-box}
html,body{background:var(--bg);color:var(--fg);margin:0}
body{font-family:var(--body);font-size:16px;line-height:1.5;padding-left:max(16px,env(safe-area-inset-left,0px));padding-right:max(16px,env(safe-area-inset-right,0px));padding-block:20px 40px}
.wrap{max-width:1100px;margin:0 auto;display:flex;flex-direction:column;gap:18px}
header{display:flex;flex-wrap:wrap;align-items:baseline;justify-content:space-between;gap:8px 20px}
h1{font-family:var(--display);font-weight:700;font-size:clamp(26px,4.4vw,44px);line-height:1.05;margin:0;letter-spacing:.02em;color:var(--glow);text-shadow:0 0 18px rgba(255,215,94,.45),3px 3px 0 #5b3a00;text-wrap:balance}
.sub{color:var(--muted);margin:0;font-weight:700}
.screen{position:relative;width:100%;max-width:100%;aspect-ratio:16/9;background:#000;border:3px solid var(--line);border-radius:6px;overflow:hidden;box-shadow:0 0 0 3px #000,0 18px 50px rgba(0,0,0,.5);touch-action:none;user-select:none;-webkit-user-select:none}
canvas{display:block;width:100%;height:100%;image-rendering:pixelated}
.overlay{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;padding:3%;background:rgba(10,8,22,.72)}
.card{background:var(--panel);border:3px solid var(--line);border-radius:6px;padding:clamp(12px,2.4vw,26px);width:min(640px,100%);max-height:100%;overflow:auto;box-shadow:6px 6px 0 #000}
.card h2{font-family:var(--display);font-size:clamp(17px,2.6vw,28px);margin:0 0 6px;color:var(--glow);line-height:1.15;text-wrap:balance}
.card .tag{font-family:var(--display);font-size:clamp(10px,1.3vw,13px);letter-spacing:.08em;color:var(--glow2);text-transform:uppercase;margin:0 0 4px}
.card p{margin:0 0 10px;font-size:clamp(13px,1.7vw,17px)}
.card ul{margin:0 0 12px;padding-left:20px;font-size:clamp(13px,1.6vw,16px)}
.opts{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin:10px 0}
@media (max-width:560px){.opts{grid-template-columns:1fr}}
button{font-family:var(--body);font-weight:800;cursor:pointer}
.opt{background:#2a2550;color:var(--fg);border:2px solid var(--line);border-radius:4px;padding:10px 12px;text-align:left;font-size:clamp(13px,1.7vw,16px);box-shadow:3px 3px 0 #000}
.opt:hover:not(:disabled){border-color:var(--glow2);background:#332d63}
.opt:disabled{opacity:.45;cursor:default}
.opt.right{background:#1f4a2c;border-color:var(--good);opacity:1}
.opt .k{font-family:var(--display);color:var(--glow2);margin-right:8px}
.go{background:var(--glow);color:#2a1a00;border:0;border-radius:4px;padding:10px 18px;font-size:clamp(14px,1.8vw,18px);box-shadow:3px 3px 0 #000;font-family:var(--display)}
.go:hover{filter:brightness(1.08)}
button:focus-visible,input:focus-visible{outline:3px solid var(--glow2);outline-offset:2px}
.fb{border-radius:4px;padding:8px 10px;margin:6px 0 10px;font-size:clamp(13px,1.6vw,16px)}
.fb.ok{background:#173b22;border:2px solid var(--good)}
.fb.no{background:#43201b;border:2px solid var(--bad)}
.row{display:flex;flex-wrap:wrap;gap:10px;align-items:center}
label{font-weight:800}
input[type=text]{font-family:var(--body);font-size:16px;padding:8px 10px;border-radius:4px;border:2px solid var(--line);background:#100e1e;color:var(--fg);width:min(260px,100%)}
.code{font-family:var(--display);font-size:clamp(26px,5vw,48px);letter-spacing:.18em;color:var(--glow);text-shadow:0 0 16px rgba(255,215,94,.6);margin:6px 0 8px;word-break:break-all}
.cert{border:2px dashed var(--glow);border-radius:6px;padding:12px;margin:10px 0}
.touch{position:absolute;left:0;right:0;bottom:0;display:flex;justify-content:space-between;padding:0 2% 2%;pointer-events:none}
.touch .grp{display:flex;gap:10px;pointer-events:auto}
.tb{width:clamp(48px,9vw,74px);height:clamp(48px,9vw,74px);border-radius:50%;border:3px solid rgba(255,255,255,.5);background:rgba(20,16,40,.55);color:#fff;font-size:clamp(18px,3vw,28px);font-family:var(--display)}
.tb.on{background:rgba(110,240,255,.35)}
.hud-btn{position:absolute;top:1.4%;right:1%;display:flex;gap:6px}
.hud-btn button{background:rgba(20,16,40,.7);color:#fff;border:2px solid rgba(255,255,255,.35);border-radius:4px;padding:4px 8px;font-size:clamp(10px,1.3vw,13px);font-family:var(--display)}
.below{display:grid;grid-template-columns:1fr 1fr;gap:18px}
@media (max-width:760px){.below{grid-template-columns:1fr}}
.box{background:var(--panel);border:2px solid var(--line);border-radius:6px;padding:14px 16px;min-width:0}
.box h3{font-family:var(--display);font-size:16px;margin:0 0 8px;color:var(--glow2);letter-spacing:.04em}
.keys{display:grid;grid-template-columns:auto 1fr;gap:6px 12px;font-size:15px}
kbd{font-family:var(--display);font-size:12px;background:#2a2550;border:1px solid var(--line);border-bottom-width:3px;border-radius:3px;padding:2px 6px;white-space:nowrap}
details summary{cursor:pointer;font-weight:800}
details ul{padding-left:20px;margin:8px 0 0}
@media (prefers-reduced-motion:reduce){*{transition:none!important;animation:none!important}}
</style>

</head>
<body>
<div class="wrap">
  <header>
    <h1>Endodragon Quest</h1>
    <p class="sub">4th Grade Science: Animal Armor, Plant Parts, and Cells</p>
  </header>

  <div class="screen" id="screen">
    <canvas id="cv" width="960" height="540" aria-label="Endodragon Quest game screen"></canvas>
    <div class="hud-btn"><button id="btnSound" type="button">Sound: off</button><button id="btnPause" type="button">Pause</button></div>
    <div class="touch" id="touch" hidden>
      <div class="grp"><button class="tb" id="tL" type="button" aria-label="Move left">&lt;</button><button class="tb" id="tR" type="button" aria-label="Move right">&gt;</button></div>
      <div class="grp"><button class="tb" id="tE" type="button" aria-label="Use glowing block">?</button><button class="tb" id="tJ" type="button" aria-label="Jump">^</button></div>
    </div>
    <div class="overlay" id="ov"><div class="card" id="card"></div></div>
  </div>

  <div class="below">
    <div class="box">
      <h3>How to play</h3>
      <div class="keys">
        <span><kbd>A</kbd> <kbd>D</kbd> or <kbd>&larr;</kbd> <kbd>&rarr;</kbd></span><span>Walk</span>
        <span><kbd>Space</kbd> <kbd>W</kbd> <kbd>&uarr;</kbd></span><span>Jump</span>
        <span><kbd>E</kbd> or bump it</span><span>Open a glowing <b>?</b> block</span>
        <span><kbd>1</kbd> to <kbd>4</kbd></span><span>Pick an answer</span>
        <span><kbd>P</kbd></span><span>Pause</span>
      </div>
      <p style="margin:10px 0 0;color:var(--muted)">Answer all 3 glowing blocks in a biome to open the dragon gate. In the boss arena, touch a glowing crystal and answer right to blast the Endodragon. Each glowing block gives you one letter of the secret code.</p>
    </div>
    <div class="box">
      <h3>For teachers</h3>
      <details>
        <summary>What the game covers</summary>
        <ul>
          <li><b>LS 4-LS1-1:</b> plants and animals have internal and external structures that help them survive, grow, behave, and reproduce.</li>
          <li><b>Biome 1, Armor Bayou:</b> external animal structures for protection (shells, scales, quills, exoskeletons, fur, horns, camouflage, warning colors), with Louisiana and U.S. park animals.</li>
          <li><b>Biome 2, Root and Leaf Forest:</b> roots, stems, leaves, flowers, seeds, thorns, and growth support.</li>
          <li><b>Biome 3, Cell Caverns:</b> cell theory, nucleus, membrane, cell wall, cytoplasm, chloroplasts, mitochondria, vacuoles, plant vs. animal cells.</li>
          <li>Students who finish see a certificate with their name, the 9 letter secret code, and their first try score. Have them screenshot it or type the code into your assignment.</li>
        </ul>
      </details>
    </div>
  </div>
</div>

<script>
(()=>{
"use strict";
const cv=document.getElementById('cv'),ctx=cv.getContext('2d');
const VW=960,VH=540,T=36,W=150,H=15;
const dpr=Math.min(2,window.devicePixelRatio||1);
cv.width=VW*dpr;cv.height=VH*dpr;ctx.setTransform(dpr,0,0,dpr,0,0);ctx.imageSmoothingEnabled=false;
const reduceMotion=matchMedia('(prefers-reduced-motion: reduce)').matches;
const CODE="STRUCTURE";

/* ---------- QUESTIONS ---------- */
const QB=[
[ // World 1: Animal armor
{q:"A turtle pulls into its hard shell when a predator comes near. What job does the shell do?",a:["Protects the turtle","Helps it find food","Helps it breathe underwater","Helps it see at night"],c:0,why:"A shell is an external structure. It is hard armor on the outside of the body that keeps soft parts safe."},
{q:"Which external structure keeps a porcupine safe from predators?",a:["Sharp quills","Long whiskers","Webbed feet","A curly tail"],c:0,why:"Quills are stiff, sharp hairs. A predator that bites a porcupine gets a mouth full of quills!"},
{q:"The nine banded armadillo lives in Louisiana. Its body is covered in hard, bony plates. What do the plates do?",a:["Protect it from predators and thorny brush","Keep it cool in summer","Help it swim fast","Help it climb trees"],c:0,why:"The armadillo's bony shell works like a suit of armor on the outside of its body."},
{q:"An alligator's back is covered with hard, bumpy scales. This is an example of...",a:["An external structure for protection","An internal structure","A plant part","A cell organelle"],c:0,why:"External means on the outside. The alligator's tough scales are armor on the outside of its body."},
{q:"A crawfish has a hard covering on the OUTSIDE of its body instead of bones inside. What is it called?",a:["Exoskeleton","Endoskeleton","Cell wall","Fur coat"],c:0,why:"Exo means outside. Crawfish, crabs, and insects have an exoskeleton. Endo means inside, like your bones."},
{q:"A green anole lizard can turn brown to match a tree branch. How does this help it?",a:["It hides from predators","It gets taller","It makes its own food","It grows a new tail"],c:0,why:"Blending in is called camouflage. If a hawk cannot see the lizard, it cannot catch it."},
{q:"Which of these is an INTERNAL structure?",a:["Heart","Shell","Scales","Quills"],c:0,why:"Internal means inside the body. The heart is inside. Shells, scales, and quills are on the outside."},
{q:"Bison in Yellowstone National Park live through freezing winters. Which structure helps them survive the cold?",a:["Thick, shaggy fur","Bright red feathers","A hard shell","Thin, smooth skin"],c:0,why:"Thick fur traps warm air next to the body, like wearing a heavy winter coat."},
{q:"Bighorn sheep in U.S. parks have big, curled horns. How do horns help them?",a:["Defend themselves and protect their heads","Help them breathe","Help them see in the dark","Make food from sunlight"],c:0,why:"Horns are tough external structures used for defense and for head butting contests."},
{q:"A poison dart frog has very bright colors. What do the bright colors tell predators?",a:["Stay away, I am dangerous to eat","Come eat me","I am a plant","I am sleeping"],c:0,why:"Bright warning colors are a kind of protection. They warn predators that the animal tastes bad or is poisonous."},
{q:"What does the word EXTERNAL mean?",a:["On the outside of the body","Inside the body","Under the ground","Up in the sky"],c:0,why:"External structures are on the outside, like skin, shells, fur, and claws."},
{q:"A snail is soft and slow. What external structure protects it?",a:["Its spiral shell","Its quills","Its feathers","Its antlers"],c:0,why:"The snail can pull its soft body into its shell to hide from birds and to stay moist."}
],
[ // World 2: Plant parts
{q:"Which plant part takes in water and minerals from the soil?",a:["Roots","Leaves","Flowers","Seeds"],c:0,why:"Roots grow down into the soil, soak up water and minerals, and hold the plant in place."},
{q:"Besides drinking water, roots also...",a:["Anchor the plant in the ground","Make the plant's flowers","Make seeds","Catch sunlight"],c:0,why:"Roots hold on tight to the soil so wind and rain cannot pull the plant out."},
{q:"Which plant part holds the plant up and carries water from the roots to the leaves?",a:["Stem","Flower","Seed","Thorn"],c:0,why:"The stem is the plant's support. Tiny tubes inside it carry water up and food down."},
{q:"Which plant part uses sunlight, water, and air to make food for the plant?",a:["Leaves","Roots","Seeds","Thorns"],c:0,why:"Leaves make food through photosynthesis. They are like little solar panels."},
{q:"What is the main job of a flower?",a:["Make seeds so new plants can grow","Soak up water","Hold the plant up","Scare away animals"],c:0,why:"Flowers are for reproduction. With help from pollinators like bees, flowers make seeds."},
{q:"A seed is planted and watered. What can it grow into?",a:["A new plant","A rock","An animal","A cloud"],c:0,why:"A seed holds a tiny baby plant and stored food. With water and warmth it sprouts."},
{q:"A rose bush has sharp thorns on its stem. How do thorns help the plant?",a:["Protect it from animals that want to eat it","Help it drink water","Make food","Make seeds"],c:0,why:"Thorns are a plant's armor. Animals learn to stay away from sharp stems."},
{q:"A tree trunk is really a big, woody...",a:["Stem","Root","Leaf","Flower"],c:0,why:"A trunk is a thick, strong stem. It supports the tree so its leaves can reach the sunlight."},
{q:"When you eat a carrot, which plant part are you eating?",a:["Root","Leaf","Flower","Stem"],c:0,why:"A carrot is a root that stores extra food for the plant."},
{q:"A pea plant has curly tendrils that wrap around a fence. Why?",a:["To climb up toward the sunlight","To dig into the soil","To make seeds","To scare birds"],c:0,why:"Tendrils are growth support. They help a weak stem climb higher to get more sunlight."},
{q:"A cactus has a thick, waxy stem. How does that help it in the desert?",a:["It stores water and keeps it from drying out","It helps it swim","It makes it grow flowers all year","It helps it walk"],c:0,why:"The waxy coating keeps water inside, and the thick stem stores water for dry days."},
{q:"Water travels from the roots up to the leaves through tiny tubes in the...",a:["Stem","Flower","Seed","Petals"],c:0,why:"Stems have tube like structures that work like straws to move water up the plant."}
],
[ // World 3: Cells
{q:"The cell theory says that ALL living things are made of...",a:["Cells","Rocks","Water only","Metal"],c:0,why:"From the tiniest bacteria to the biggest whale, every living thing is made of one or more cells."},
{q:"The cell theory says the cell is...",a:["The basic unit of life","A kind of rock","Only found in plants","Bigger than an animal"],c:0,why:"A cell is the smallest unit that can be alive. Cells are the building blocks of living things."},
{q:"Where do new cells come from?",a:["From cells that already exist","From dirt","From sunlight","From nowhere"],c:0,why:"This is the third part of the cell theory. Cells divide to make new cells."},
{q:"Which cell part is the control center that holds the DNA?",a:["Nucleus","Cell membrane","Vacuole","Cytoplasm"],c:0,why:"The nucleus is like the brain of the cell. It holds the instructions, called DNA."},
{q:"Which cell part is like a security guard that controls what goes in and out?",a:["Cell membrane","Nucleus","Chloroplast","Vacuole"],c:0,why:"The cell membrane is a thin covering that lets good things in and keeps waste moving out."},
{q:"Which stiff outer layer gives plant cells extra support but is NOT in animal cells?",a:["Cell wall","Nucleus","Cell membrane","Cytoplasm"],c:0,why:"The cell wall is a strong box around a plant cell. It helps plants stand up tall."},
{q:"Which part of a plant cell captures sunlight to make food?",a:["Chloroplast","Mitochondria","Nucleus","Cell membrane"],c:0,why:"Chloroplasts are green and use sunlight to make food. Animal cells do not have them."},
{q:"Which cell part is called the powerhouse because it releases energy?",a:["Mitochondria","Vacuole","Cell wall","Chloroplast"],c:0,why:"Mitochondria break down food to release energy the cell can use."},
{q:"What is the jelly like fluid that fills the cell and holds the parts in place?",a:["Cytoplasm","Cell wall","Nucleus","Seed"],c:0,why:"Cytoplasm is the jelly inside the cell where all the organelles float."},
{q:"Which cell part stores water and is usually very big in plant cells?",a:["Vacuole","Nucleus","Mitochondria","Membrane"],c:0,why:"The vacuole is a storage tank. A full vacuole helps keep a plant from wilting."},
{q:"Cells are too small to see with just your eyes. What tool do scientists use?",a:["Microscope","Telescope","Thermometer","Ruler"],c:0,why:"A microscope makes tiny things look much bigger so we can see cells."},
{q:"Robert Hooke looked at a thin slice of cork in 1665 and named the tiny boxes he saw. What did he call them?",a:["Cells","Rooms","Bricks","Seeds"],c:0,why:"Hooke thought the boxes looked like little rooms, called cells. The name stuck!"}
]];

/* ---------- WORLDS ---------- */
const WORLDS=[
{name:"Armor Bayou",tag:"Biome 1 of 3",boss:"Shellback the Endodragon",bossHp:3,fire:2.3,seed:11,
 learn:["External structures are on the OUTSIDE of an animal's body.","Shells, scales, quills, exoskeletons, thick fur, and horns protect animals.","Camouflage and warning colors help animals hide or warn predators."],
 sky:["#2c6d73","#8fc7a5"],far:"#235048",grass:"#5aa83c",grass2:"#3f8a2c",dirt:"#7a5230",dirt2:"#5e3f24",stone:"#6c6f63",plank:"#8a6a3c",plank2:"#6b5030",water:"rgba(40,110,90,.8)",glow:"#ffd75e",mob:"crawfish"},
{name:"Root and Leaf Forest",tag:"Biome 2 of 3",boss:"Thornroot the Endodragon",bossHp:3,fire:1.9,seed:27,
 learn:["Roots soak up water and anchor the plant.","Stems hold the plant up and carry water. Leaves make food from sunlight.","Flowers make seeds, seeds grow new plants, and thorns protect."],
 sky:["#4a9be0","#c8ecff"],far:"#4d8f5a",grass:"#63c94a",grass2:"#45a336",dirt:"#8b5a35",dirt2:"#6c4428",stone:"#7b7e86",plank:"#3f9a3f",plank2:"#2c7a32",water:"rgba(60,120,210,.8)",glow:"#b8ff5e",mob:"beetle"},
{name:"Cell Caverns",tag:"Biome 3 of 3",boss:"Nucleon the Endodragon",bossHp:4,fire:1.6,seed:53,
 learn:["Cell theory: all living things are made of cells, cells are the basic unit of life, and cells come from other cells.","The nucleus is the control center. The membrane controls what goes in and out.","Plant cells also have a cell wall, chloroplasts, and a big vacuole."],
 sky:["#140d2e","#2d1a52"],far:"#2a1c4d",grass:"#d46fb3",grass2:"#a64d8e",dirt:"#5a2f6e",dirt2:"#45235a",stone:"#3d3566",plank:"#4fc3c9",plank2:"#2e8f99",water:"rgba(160,90,220,.75)",glow:"#6ef0ff",mob:"germ"}
];

/* ---------- STATE ---------- */
const S={mode:'title',world:0,name:'',hearts:5,maxHearts:5,gems:0,letters:[],firstTry:0,answered:0,startTime:0,endTime:0,sound:false,paused:false};
let L=null; // level
let P=null; // player
let cam=0,shake=0,particles=[],fireballs=[],toasts=[],beams=[];
const keys={};

function rng(seed){let a=seed>>>0;return()=>{a|=0;a=a+0x6D2B79F5|0;let t=Math.imul(a^a>>>15,1|a);t=t+Math.imul(t^t>>>7,61|t)^t;return((t^t>>>14)>>>0)/4294967296}}
const hash=(x,y)=>{let h=x*374761393+y*668265263;h=(h^(h>>>13))*1274126177;return((h^(h>>>16))>>>0)/4294967296};

const SOLID=new Set([1,2,3,7,8,9,10,11]);
function buildLevel(w){
  const Wd=WORLDS[w],r=rng(Wd.seed);
  const t=new Uint8Array(W*H),gy=new Array(W).fill(11);
  const Q=[22,55,88],CP=[3,40,75,113],GATE=117;
  const prot=x=>x<6||x>=108||Q.some(q=>Math.abs(q-x)<=3)||CP.some(c=>Math.abs(c-x)<=1);
  let g=11;
  for(let x=0;x<W;x++){ if(x%7===0&&x>6&&x<106){const d=[-1,0,1][Math.floor(r()*3)];g=Math.max(9,Math.min(12,g+d));} gy[x]=x>=106?11:g; }
  // keep q-block zones flat
  Q.forEach(q=>{for(let i=q-3;i<=q+3;i++)gy[i]=gy[q-3]});
  const gaps=[];
  [14,32,47,66,80,100].forEach(gx=>{const len=2+Math.floor(r()*2);if(!prot(gx)&&!prot(gx+len)){gaps.push([gx,len]);for(let i=gx-1;i<=gx+len+2&&i<106;i++)gy[i]=gy[gx-1];}});
  const isGap=x=>gaps.some(([a,l])=>x>=a&&x<a+l);
  for(let x=0;x<W;x++){
    if(isGap(x)){t[13*W+x]=6;t[14*W+x]=6;continue}
    for(let y=gy[x];y<H;y++)t[y*W+x]=y===gy[x]?1:(y>gy[x]+2?3:2);
  }
  // glow lamp blocks set into the ground
  for(let x=8;x<104;x++){ if(!isGap(x)&&!prot(x)&&r()<(w===2?0.14:0.05)) t[gy[x]*W+x]=11; }
  // floating platforms with gems
  const gems=[];
  [28,62,95,105].forEach(px=>{const y=gy[px]-4;for(let i=0;i<3;i++)t[y*W+px+i]=10;for(let i=0;i<3;i++)gems.push({x:(px+i)*T+T/2,y:(y-1)*T+T/2,got:false});});
  // ground gems in arcs over gaps
  gaps.forEach(([a,l])=>{for(let i=0;i<l;i++)gems.push({x:(a+i)*T+T/2,y:(gy[a-1]-3)*T,got:false})});
  // question blocks
  const qb=Q.map((qx,i)=>{const y=gy[qx]-4;t[y*W+qx]=7;return{tx:qx,ty:y,i,done:false,letter:CODE[w*3+i]}});
  // gate
  for(let y=0;y<11;y++)t[y*W+GATE]=9;
  // arena
  for(let y=0;y<H;y++)t[y*W+(W-1)]=3;
  [[124,8,4],[136,8,4],[130,5,4]].forEach(([x,y,n])=>{for(let i=0;i<n;i++)t[y*W+x+i]=10});
  const crystals=[{x:120.5*T,y:11*T,ready:true,cd:0},{x:132*T,y:5*T,ready:true,cd:0},{x:145.5*T,y:11*T,ready:true,cd:0}];
  // mobs
  const mobs=[];
  [18,36,51,71,84,98].forEach(mx=>{if(!isGap(mx)&&!Q.some(q=>Math.abs(q-mx)<2))mobs.push({x:mx*T,y:gy[mx]*T-24,w:30,h:24,vx:(r()<.5?-1:1)*55,alive:true,t:r()*6})});
  // decorations
  const deco=[];
  for(let x=4;x<106;x+=3+Math.floor(r()*4)){ if(isGap(x)||isGap(x+1))continue; deco.push({x,y:gy[x],k:Math.floor(r()*3),s:r()}); }
  const cps=CP.map(c=>({x:c*T,y:gy[c]*T,on:c===3}));
  cps.push({x:121*T,y:11*T,on:false,arena:true});
  return{t,gy,qb,gems,crystals,mobs,deco,cps,gate:GATE,gateOpen:false,arenaX:118*T,inArena:false,boss:null,bossDone:false,cp:{x:3*T,y:gy[3]*T},used:new Set(),gaps};
}
const tile=(x,y)=>(x<0||x>=W)?3:(y<0||y>=H)?0:L.t[y*W+x];
const solidAt=(x,y)=>SOLID.has(tile(x,y));

function newPlayer(x,y){return{x:x-13,y:y-46,w:26,h:46,vx:0,vy:0,face:1,ground:false,coyote:0,buf:0,inv:0,walk:0}}

/* ---------- AUDIO ---------- */
let AC=null;
function beep(f,d=.08,type='square',v=.05){ if(!S.sound)return; try{ AC=AC||new (window.AudioContext||window.webkitAudioContext)(); const o=AC.createOscillator(),g=AC.createGain(); o.type=type;o.frequency.value=f;g.gain.value=v;o.connect(g);g.connect(AC.destination);const n=AC.currentTime;g.gain.exponentialRampToValueAtTime(.0001,n+d);o.start(n);o.stop(n+d);}catch(e){} }
const sfx={jump:()=>beep(520,.07),gem:()=>{beep(880,.06,'triangle');setTimeout(()=>beep(1320,.08,'triangle'),60)},right:()=>{[660,880,1100].forEach((f,i)=>setTimeout(()=>beep(f,.1,'triangle',.06),i*90))},wrong:()=>beep(160,.2,'sawtooth',.04),hit:()=>beep(110,.15,'square',.06),boom:()=>{for(let i=0;i<6;i++)setTimeout(()=>beep(90+Math.random()*120,.18,'sawtooth',.05),i*70)}};

/* ---------- OVERLAY UI ---------- */
const ov=document.getElementById('ov'),card=document.getElementById('card');
function show(html){card.innerHTML=html;ov.hidden=false;const f=card.querySelector('button,input');if(f)setTimeout(()=>f.focus(),30)}
function hide(){ov.hidden=true;cv.focus?.()}
const esc=s=>String(s).replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));

function titleScreen(){
  S.mode='title';
  show(`<p class="tag">A blocky science adventure</p><h2>Endodragon Quest</h2>
  <p>Three Endodragons have taken over the biomes! Each one is a dragon with a glowing endoskeleton, bones on the INSIDE. Jump through each biome, open the glowing <b>?</b> blocks, and answer science questions to beat them.</p>
  <ul><li>Biome 1: Armor Bayou (animal protection)</li><li>Biome 2: Root and Leaf Forest (plant parts)</li><li>Biome 3: Cell Caverns (cells)</li></ul>
  <p>Collect all 9 code letters to unlock the secret code at the end.</p>
  <div class="row"><label for="nm">Your first name</label><input type="text" id="nm" maxlength="20" autocomplete="off" placeholder="First name"></div>
  <div class="row" style="margin-top:12px"><button class="go" id="bStart" type="button">Start Quest</button></div>`);
  const nm=document.getElementById('nm');
  document.getElementById('bStart').onclick=()=>{S.name=(nm.value||'').trim().slice(0,20);S.startTime=performance.now();S.letters=[];S.gems=0;S.firstTry=0;S.answered=0;S.world=0;worldIntro()};
  nm.addEventListener('keydown',e=>{if(e.key==='Enter')document.getElementById('bStart').click()});
}
function worldIntro(){
  const w=WORLDS[S.world];
  L=buildLevel(S.world);P=newPlayer(L.cp.x+T/2,L.cp.y);S.hearts=S.maxHearts;cam=0;particles=[];fireballs=[];beams=[];toasts=[];
  L.qpool=shuffle([...Array(QB[S.world].length).keys()]);
  S.mode='intro';
  show(`<p class="tag">${w.tag}</p><h2>${esc(w.name)}</h2><p><b>Learn it before you jump in:</b></p>
  <ul>${w.learn.map(x=>`<li>${esc(x)}</li>`).join('')}</ul>
  <p>Find the 3 glowing <b>?</b> blocks. Then face <b>${esc(w.boss)}</b>.</p>
  <button class="go" id="bGo" type="button">Let's go!</button>`);
  document.getElementById('bGo').onclick=()=>{hide();S.mode='play'};
}
function shuffle(a){for(let i=a.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[a[i],a[j]]=[a[j],a[i]]}return a}
function nextQ(){ if(!L.qpool.length)L.qpool=shuffle([...Array(QB[S.world].length).keys()]); return QB[S.world][L.qpool.pop()] }

function ask(kind,onDone){
  S.mode='question';
  const Q=nextQ(),opts=shuffle(Q.a.map((t,i)=>({t,ok:i===Q.c})));
  let tries=0;
  const head=kind==='boss'?`<p class="tag">Power crystal</p><h2>Blast the Endodragon!</h2>`:`<p class="tag">Glowing block</p><h2>Science check</h2>`;
  show(`${head}<p style="font-weight:800">${esc(Q.q)}</p><div class="opts">${opts.map((o,i)=>`<button class="opt" type="button" data-i="${i}"><span class="k">${i+1}</span>${esc(o.t)}</button>`).join('')}</div><div id="fbx"></div>`);
  const btns=[...card.querySelectorAll('.opt')];
  const pick=i=>{
    const b=btns[i];if(!b||b.disabled)return;
    tries++;
    const fb=document.getElementById('fbx');
    if(opts[i].ok){
      if(tries===1)S.firstTry++;S.answered++;
      btns.forEach(x=>x.disabled=true);b.classList.add('right');sfx.right();
      fb.innerHTML=`<div class="fb ok"><b>Correct!</b> ${esc(Q.why)}</div><button class="go" id="bC" type="button">${kind==='boss'?'Fire the beam!':'Collect letter'}</button>`;
      document.getElementById('bC').onclick=()=>{hide();S.mode='play';onDone(true)};
    }else{
      b.disabled=true;sfx.wrong();
      if(kind==='boss'){
        btns.forEach(x=>x.disabled=true);
        fb.innerHTML=`<div class="fb no"><b>Not this time.</b> The answer was <b>${esc(Q.a[Q.c])}</b>. ${esc(Q.why)}</div><button class="go" id="bC" type="button">Back to the fight</button>`;
        document.getElementById('bC').onclick=()=>{hide();S.mode='play';onDone(false)};
      }else{
        fb.innerHTML=`<div class="fb no"><b>Good try!</b> That one is not it. Read the question again and pick another answer.</div>`;
      }
    }
  };
  btns.forEach((b,i)=>b.onclick=()=>pick(i));
  ask.pick=pick;
}

/* ---------- INPUT ---------- */
const K={left:['ArrowLeft','KeyA'],right:['ArrowRight','KeyD'],jump:['Space','ArrowUp','KeyW'],use:['KeyE']};
const down=a=>K[a].some(k=>keys[k])||touch[a];
const touch={left:false,right:false,jump:false,use:false};
addEventListener('keydown',e=>{
  if(S.mode==='question'&&/^Digit[1-4]$/.test(e.code)){ask.pick&&ask.pick(+e.code.slice(5)-1);return}
  if(e.target&&e.target.tagName==='INPUT')return;
  if(S.mode==='play'||S.mode==='paused'){ if(['Space','ArrowUp','ArrowDown','ArrowLeft','ArrowRight'].includes(e.code))e.preventDefault(); }
  if(e.code==='KeyP'||e.code==='Escape'){togglePause();return}
  if(!keys[e.code]&&K.jump.includes(e.code)&&P)P.buf=.13;
  if(!keys[e.code]&&e.code==='KeyE')tryUse();
  keys[e.code]=true;
});
addEventListener('keyup',e=>{keys[e.code]=false});
addEventListener('blur',()=>{for(const k in keys)keys[k]=false});
function bindTouch(id,a){const el=document.getElementById(id);
  const on=e=>{e.preventDefault();touch[a]=true;el.classList.add('on');if(a==='jump'&&P)P.buf=.13;if(a==='use')tryUse()};
  const off=e=>{e.preventDefault();touch[a]=false;el.classList.remove('on')};
  el.addEventListener('pointerdown',on);el.addEventListener('pointerup',off);el.addEventListener('pointerleave',off);el.addEventListener('pointercancel',off);}
bindTouch('tL','left');bindTouch('tR','right');bindTouch('tJ','jump');bindTouch('tE','use');
const tc=document.getElementById('touch');
if(matchMedia('(pointer: coarse)').matches)tc.hidden=false;
addEventListener('touchstart',()=>{tc.hidden=false},{once:true,passive:true});
const bS=document.getElementById('btnSound'),bP=document.getElementById('btnPause');
bS.onclick=()=>{S.sound=!S.sound;bS.textContent='Sound: '+(S.sound?'on':'off');if(S.sound)beep(660,.08)};
bP.onclick=togglePause;
function togglePause(){ if(S.mode==='play'){S.mode='paused';bP.textContent='Resume';show(`<h2>Paused</h2><p>Take a breath, scientist.</p><button class="go" id="bR" type="button">Resume</button>`);document.getElementById('bR').onclick=togglePause;}
  else if(S.mode==='paused'){S.mode='play';bP.textContent='Pause';hide();} }

function tryUse(){
  if(S.mode!=='play'||!P)return;
  const cx=P.x+P.w/2;
  for(const b of L.qb){ if(b.done)continue; const bx=b.tx*T+T/2,by=b.ty*T+T; if(Math.abs(bx-cx)<T*1.6&&P.y-by<T*2.2&&P.y-by>-T){openBlock(b);return} }
  for(const c of L.crystals){ if(c.ready&&L.boss&&!L.bossDone&&Math.abs(c.x-cx)<T*1.4&&Math.abs((c.y-20)-(P.y+P.h/2))<T*1.6){useCrystal(c);return} }
}

/* ---------- GAME EVENTS ---------- */
function toast(t,c='#fff'){toasts.push({t,c,life:2.8});if(toasts.length>3)toasts.shift()}
function burst(x,y,col,n=18,sp=220){for(let i=0;i<n;i++){const a=Math.random()*Math.PI*2,s=sp*(.3+Math.random());particles.push({x,y,vx:Math.cos(a)*s,vy:Math.sin(a)*s-80,life:.6+Math.random()*.6,col,sz:3+Math.random()*4})}}
function openBlock(b){
  ask('block',()=>{
    b.done=true;L.t[b.ty*W+b.tx]=8;S.letters.push(b.letter);sfx.gem();
    burst(b.tx*T+T/2,b.ty*T,WORLDS[S.world].glow,26);
    toast(`Code letter found: ${b.letter}`,WORLDS[S.world].glow);
    if(L.qb.every(q=>q.done)){L.gateOpen=true;for(let y=0;y<11;y++){L.t[y*W+L.gate]=0;burst(L.gate*T+T/2,y*T+T/2,'#ff7ad9',4,120)}toast('The dragon gate is open! Head right.','#ff9be6');}
  });
}
function useCrystal(c){
  c.ready=false;
  ask('boss',ok=>{
    if(ok){beams.push({x:c.x,y:c.y-30,life:.6});setTimeout(()=>hitBoss(),350);c.cd=4}
    else{c.cd=2;const B=L.boss;if(B)fireballs.push({x:B.x,y:B.y+30,vx:(P.x-B.x)*.6,vy:200,r:12})}
  });
}
function hitBoss(){
  const B=L.boss;if(!B||L.bossDone)return;
  B.hp--;B.flash=.5;sfx.hit();shake=reduceMotion?0:10;burst(B.x,B.y,'#fff',30,300);
  if(B.hp<=0){L.bossDone=true;sfx.boom();shake=reduceMotion?0:18;fireballs=[];
    for(let i=0;i<5;i++)setTimeout(()=>burst(B.x+(Math.random()-.5)*120,B.y+(Math.random()-.5)*60,WORLDS[S.world].glow,40,360),i*180);
    setTimeout(bossWin,1400);
  }else toast(`${B.hp} hit${B.hp>1?'s':''} left!`,'#fff');
}
function bossWin(){
  S.mode='bossWin';const w=WORLDS[S.world];const got=S.letters.join('');
  const last=S.world===2;
  show(`<p class="tag">Boss defeated</p><h2>You beat ${esc(w.boss)}!</h2>
  <p>Code letters so far:</p><div class="code">${esc(got.padEnd(9,'_'))}</div>
  <button class="go" id="bN" type="button">${last?'See the secret code':'Next biome'}</button>`);
  document.getElementById('bN').onclick=()=>{ if(last){finish()}else{S.world++;worldIntro()} };
}
function finish(){
  S.mode='end';S.endTime=performance.now();
  const secs=Math.round((S.endTime-S.startTime)/1000),m=Math.floor(secs/60),s=secs%60;
  const pct=S.answered?Math.round(S.firstTry/S.answered*100):0;
  const code=S.letters.length===9?S.letters.join(''):CODE;
  show(`<p class="tag">Quest complete</p><h2>All three Endodragons are defeated!</h2>
  <div class="cert">
    <p style="margin:0"><b>${esc(S.name||'Scientist')}</b>, your secret code is:</p>
    <div class="code">${esc(code)}</div>
    <p style="margin:0">Plants and animals have internal and external <b>structures</b> that help them survive, grow, and reproduce. Shells, roots, leaves, and cell parts are all structures!</p>
    <p style="margin:8px 0 0">First try answers: <b>${S.firstTry} of ${S.answered}</b> (${pct}%) &nbsp; Glow gems: <b>${S.gems}</b> &nbsp; Time: <b>${m}m ${s}s</b></p>
  </div>
  <p>Take a screenshot of this certificate or type the code into your assignment for your teacher.</p>
  <button class="go" id="bA" type="button">Play again</button>`);
  document.getElementById('bA').onclick=titleScreen;
  sfx.right();
}
function hurt(from){
  if(P.inv>0)return;S.hearts--;P.inv=1.4;sfx.hit();shake=reduceMotion?0:6;
  P.vx=(P.x+P.w/2<from?-1:1)*320;P.vy=-420;
  if(S.hearts<=0){toast('Out of hearts! Back to the checkpoint.','#ff8a7a');respawn(true)}
}
function respawn(refill){P=newPlayer(L.cp.x+T/2,L.cp.y);P.inv=1.2;if(refill)S.hearts=S.maxHearts;fireballs=[]}

/* ---------- UPDATE ---------- */
function update(dt){
  const w=WORLDS[S.world];
  // player
  const ax=(down('right')?1:0)-(down('left')?1:0);
  const target=ax*270;P.vx+=(target-P.vx)*Math.min(1,dt*(P.ground?14:7));
  if(ax)P.face=ax;
  P.vy+=2200*dt;if(P.vy>900)P.vy=900;
  P.coyote=P.ground?.1:P.coyote-dt;P.buf-=dt;
  if(P.buf>0&&P.coyote>0){P.vy=-820;P.buf=0;P.coyote=0;sfx.jump()}
  if(!down('jump')&&P.vy<-300)P.vy+=2600*dt; // short hop
  // move x
  P.x+=P.vx*dt;
  if(P.vx>0){const tx=Math.floor((P.x+P.w)/T);for(let ty=Math.floor(P.y/T);ty<=Math.floor((P.y+P.h-1)/T);ty++)if(solidAt(tx,ty)){P.x=tx*T-P.w;P.vx=0;if(tile(tx,ty)===9)gateMsg();break}}
  else if(P.vx<0){const tx=Math.floor(P.x/T);for(let ty=Math.floor(P.y/T);ty<=Math.floor((P.y+P.h-1)/T);ty++)if(solidAt(tx,ty)){P.x=(tx+1)*T;P.vx=0;break}}
  // move y
  P.y+=P.vy*dt;P.ground=false;
  if(P.vy>0){const ty=Math.floor((P.y+P.h)/T);for(let tx=Math.floor(P.x/T);tx<=Math.floor((P.x+P.w-1)/T);tx++)if(solidAt(tx,ty)){P.y=ty*T-P.h;P.vy=0;P.ground=true;break}}
  else if(P.vy<0){const ty=Math.floor(P.y/T);for(let tx=Math.floor((P.x+2)/T);tx<=Math.floor((P.x+P.w-3)/T);tx++)if(solidAt(tx,ty)){P.y=(ty+1)*T;P.vy=60;if(tile(tx,ty)===7){const b=L.qb.find(q=>q.tx===tx&&q.ty===ty);if(b&&!b.done){burst(tx*T+T/2,(ty+1)*T,w.glow,10,140);openBlock(b)}}break}}
  if(P.ground&&Math.abs(P.vx)>20)P.walk+=dt*Math.abs(P.vx)/30;
  if(P.inv>0)P.inv-=dt;
  // fall
  if(P.y>H*T+40){toast('Splash! Back to the checkpoint.','#9fe');respawn(false)}
  // checkpoints
  for(const c of L.cps){ if(!c.on&&P.x>c.x-10&&(!c.arena||L.gateOpen)){c.on=true;L.cp={x:c.x,y:c.y};if(!c.arena)toast('Checkpoint saved','#bfffc8')} }
  // gems
  for(const g of L.gems){ if(!g.got&&Math.abs(g.x-(P.x+P.w/2))<20&&Math.abs(g.y-(P.y+P.h/2))<30){g.got=true;S.gems++;sfx.gem();burst(g.x,g.y,w.glow,8,120)} }
  // mobs
  for(const m of L.mobs){ if(!m.alive)continue; m.t+=dt;
    const nx=m.x+m.vx*dt, ahead=m.vx>0?nx+m.w:nx, footY=Math.floor((m.y+m.h+2)/T), midY=Math.floor((m.y+m.h/2)/T), tx=Math.floor(ahead/T);
    if(solidAt(tx,midY)||!solidAt(tx,footY))m.vx*=-1;else m.x=nx;
    if(P.x<m.x+m.w&&P.x+P.w>m.x&&P.y<m.y+m.h&&P.y+P.h>m.y){
      if(P.vy>80&&P.y+P.h-m.y<18){m.alive=false;P.vy=-560;S.gems++;sfx.gem();burst(m.x+m.w/2,m.y+m.h/2,'#fff',16,180);toast('Stomp! +1 gem','#fff')}
      else hurt(m.x+m.w/2);
    }
  }
  // arena + boss
  if(!L.inArena&&L.gateOpen&&P.x>L.arenaX+T*2){L.inArena=true;L.boss={x:136*T,y:3*T,hp:w.bossHp,max:w.bossHp,t:0,fire:1.5,flash:0,face:-1};toast(`${w.boss} appears!`,w.glow);sfx.boom();shake=reduceMotion?0:8}
  const B=L.boss;
  if(B&&!L.bossDone){
    B.t+=dt;const cx=(L.arenaX+(W-1)*T)/2;
    B.x=cx+Math.sin(B.t*.55)*380;B.y=3.5*T+Math.sin(B.t*1.3)*T*.8;
    B.face=(P.x<B.x)?-1:1;if(B.flash>0)B.flash-=dt;
    B.fire-=dt;if(B.fire<=0){B.fire=w.fire+Math.random()*.6;const dx=P.x+P.w/2-B.x,dy=P.y+P.h/2-B.y,d=Math.hypot(dx,dy)||1,sp=210+S.world*25;fireballs.push({x:B.x+B.face*50,y:B.y+10,vx:dx/d*sp,vy:dy/d*sp,r:11});beep(240,.1,'sawtooth',.03)}
    if(Math.abs(B.x-(P.x+P.w/2))<70&&Math.abs(B.y-(P.y+P.h/2))<40)hurt(B.x);
  }
  for(const c of L.crystals){ if(!c.ready){c.cd-=dt;if(c.cd<=0&&S.mode==='play')c.ready=true}
    if(c.ready&&B&&!L.bossDone&&S.mode==='play'&&Math.abs(c.x-(P.x+P.w/2))<22&&P.y<c.y&&P.y+P.h>c.y-44)useCrystal(c); }
  for(const f of fireballs){f.x+=f.vx*dt;f.y+=f.vy*dt;f.life=(f.life||0)+dt;
    if(solidAt(Math.floor(f.x/T),Math.floor(f.y/T))||f.life>6){f.dead=true;burst(f.x,f.y,'#ff9a3c',6,100)}
    if(!f.dead&&Math.abs(f.x-(P.x+P.w/2))<f.r+10&&Math.abs(f.y-(P.y+P.h/2))<f.r+20){f.dead=true;hurt(f.x)}}
  fireballs=fireballs.filter(f=>!f.dead);
  // camera
  let tgt=P.x+P.w/2-VW*.42;
  const minC=L.inArena?L.arenaX:0, maxC=W*T-VW;
  if(!L.gateOpen)tgt=Math.min(tgt,(L.gate+1)*T-VW+T*4);
  tgt=Math.max(minC,Math.min(maxC,tgt));cam+=(tgt-cam)*Math.min(1,dt*6);
  if(L.inArena&&P.x<L.arenaX+4){P.x=L.arenaX+4;P.vx=0}
}
let gateT=0;function gateMsg(){if(performance.now()-gateT>2500){gateT=performance.now();toast('Answer all 3 glowing blocks to open the gate!','#ff9be6')}}

function updateFx(dt){
  for(const p of particles){p.x+=p.vx*dt;p.y+=p.vy*dt;p.vy+=500*dt;p.life-=dt}
  particles=particles.filter(p=>p.life>0);
  for(const t of toasts)t.life-=dt;toasts=toasts.filter(t=>t.life>0);
  for(const b of beams)b.life-=dt;beams=beams.filter(b=>b.life>0);
  if(shake>0)shake=Math.max(0,shake-dt*30);
}

/* ---------- DRAW ---------- */
let time=0;
function draw(){
  const w=WORLDS[S.world];
  ctx.save();
  const sx=shake?(Math.random()-.5)*shake:0,sy=shake?(Math.random()-.5)*shake:0;
  // sky
  const g=ctx.createLinearGradient(0,0,0,VH);g.addColorStop(0,w.sky[0]);g.addColorStop(1,w.sky[1]);ctx.fillStyle=g;ctx.fillRect(0,0,VW,VH);
  drawBackdrop(w);
  ctx.translate(Math.round(-cam+sx),Math.round(sy));
  if(L){
    // deco behind
    for(const d of L.deco){ const px=d.x*T; if(px<cam-160||px>cam+VW+100)continue; drawDeco(d,w) }
    // tiles
    const x0=Math.max(0,Math.floor(cam/T)-1),x1=Math.min(W-1,Math.ceil((cam+VW)/T)+1);
    for(let y=0;y<H;y++)for(let x=x0;x<=x1;x++){const v=L.t[y*W+x];if(v)drawTile(v,x,y,w)}
    // checkpoints
    for(const c of L.cps){ if(c.arena)continue; drawFlag(c.x,c.y,c.on,w) }
    // gems
    for(const gm of L.gems){ if(gm.got)continue; const bob=Math.sin(time*3+gm.x)*3; glowRect(gm.x-7,gm.y-9+bob,14,18,w.glow,14); ctx.fillStyle='#fff';ctx.fillRect(gm.x-3,gm.y-6+bob,4,6) }
    // letters on used blocks
    for(const b of L.qb){ if(!b.done)continue; ctx.fillStyle=w.glow;ctx.font='700 20px Silkscreen, monospace';ctx.textAlign='center';ctx.textBaseline='middle';ctx.fillText(b.letter,b.tx*T+T/2,b.ty*T+T/2+1) }
    // crystals
    if(L.inArena)for(const c of L.crystals)drawCrystal(c,w);
    // mobs
    for(const m of L.mobs)if(m.alive)drawMob(m,w);
    // boss
    if(L.boss&&(!L.bossDone||S.mode==='play'&&false))drawDragon(L.boss,S.world);
    if(L.boss&&L.bossDone&&S.mode==='play')drawDragon(L.boss,S.world,true);
    // beams
    for(const b of beams){ if(!L.boss)continue; ctx.save();ctx.globalAlpha=Math.min(1,b.life*2);ctx.strokeStyle=w.glow;ctx.lineWidth=10;ctx.shadowColor=w.glow;ctx.shadowBlur=24;ctx.beginPath();ctx.moveTo(b.x,b.y);ctx.lineTo(L.boss.x,L.boss.y);ctx.stroke();ctx.strokeStyle='#fff';ctx.lineWidth=3;ctx.stroke();ctx.restore() }
    // fireballs
    for(const f of fireballs){ glowRect(f.x-f.r,f.y-f.r,f.r*2,f.r*2,S.world===2?'#c77dff':S.world===1?'#a3ff3c':'#ff8a2a',20);ctx.fillStyle='#fff6d0';ctx.fillRect(f.x-4,f.y-4,8,8) }
    // player
    if(P&&!(P.inv>0&&Math.floor(time*16)%2))drawPlayer(P);
    // particles
    for(const p of particles){ctx.globalAlpha=Math.max(0,Math.min(1,p.life*1.6));ctx.fillStyle=p.col;ctx.fillRect(p.x-p.sz/2,p.y-p.sz/2,p.sz,p.sz)}ctx.globalAlpha=1;
  }
  ctx.restore();
  if(L&&S.mode!=='title')drawHUD(w);
}
function glowRect(x,y,w,h,col,blur){ctx.save();ctx.shadowColor=col;ctx.shadowBlur=blur*(.75+.25*Math.sin(time*4));ctx.fillStyle=col;ctx.fillRect(x,y,w,h);ctx.restore()}
function drawBackdrop(w){
  const par=cam*.3;
  if(S.world===0){ // cypress silhouettes + moss
    ctx.fillStyle=w.far;
    for(let i=-1;i<14;i++){const bx=((i*140-par)%(14*140)+14*140)%(14*140)-140,hh=150+hash(i,3)*120;ctx.fillRect(bx+50,VH-hh-120,22,hh);ctx.fillRect(bx+20,VH-hh-150,84,40);ctx.fillRect(bx+34,VH-hh-180,56,34);ctx.fillStyle='rgba(180,200,170,.35)';ctx.fillRect(bx+28,VH-hh-110,6,40);ctx.fillRect(bx+86,VH-hh-112,6,52);ctx.fillStyle=w.far}
    ctx.fillStyle='rgba(255,240,190,.5)';ctx.fillRect(760,60,60,60);
  }else if(S.world===1){
    ctx.fillStyle='rgba(255,255,255,.75)';for(let i=0;i<6;i++){const cx=((i*220-cam*.1)%1320+1320)%1320-180;ctx.fillRect(cx,60+hash(i,9)*80,120,24);ctx.fillRect(cx+24,40+hash(i,9)*80,64,24)}
    ctx.fillStyle=w.far;for(let i=-1;i<12;i++){const bx=((i*120-par)%(12*120)+12*120)%(12*120)-120,hh=90+hash(i,5)*80;ctx.fillRect(bx,VH-hh-110,120,hh+110)}
    ctx.fillStyle='#ffe066';ctx.fillRect(820,50,54,54);
  }else{
    for(let i=0;i<34;i++){const x=((hash(i,1)*1600-cam*.2)%1600+1600)%1600-200,y=hash(i,2)*VH*.8,s=4+hash(i,4)*30,a=.15+.15*Math.sin(time*1.5+i);
      ctx.fillStyle=i%3===0?`rgba(110,240,255,${a})`:i%3===1?`rgba(255,120,210,${a})`:`rgba(170,255,140,${a})`;ctx.fillRect(x,y,s,s*.6)}
    // big floating "organelle" shapes
    ctx.fillStyle='rgba(120,70,180,.35)';for(let i=0;i<5;i++){const x=((i*360-par)%1800+1800)%1800-200,y=120+hash(i,7)*200;ctx.fillRect(x,y,120,46);ctx.fillRect(x+12,y-10,96,66)}
  }
}
function drawTile(v,x,y,w){
  const px=x*T,py=y*T,hs=hash(x,y);
  switch(v){
  case 1: ctx.fillStyle=w.dirt;ctx.fillRect(px,py,T,T);ctx.fillStyle=w.grass;ctx.fillRect(px,py,T,10);ctx.fillStyle=w.grass2;ctx.fillRect(px+(hs*5|0)*6,py+10,6,6);ctx.fillRect(px+((hs*7|0)%6)*6,py+8,6,4);dots(px,py,w.dirt2,hs,3,14);break;
  case 2: ctx.fillStyle=w.dirt;ctx.fillRect(px,py,T,T);dots(px,py,w.dirt2,hs,4,0);break;
  case 3: ctx.fillStyle=w.stone;ctx.fillRect(px,py,T,T);dots(px,py,'rgba(0,0,0,.22)',hs,4,0);break;
  case 6: { const wv=Math.sin(time*3+x)*3; ctx.fillStyle=w.water;ctx.fillRect(px,py+(y===13?8+wv:0),T,T);break }
  case 7: { ctx.save();ctx.shadowColor=w.glow;ctx.shadowBlur=18+10*Math.sin(time*5);ctx.fillStyle=w.glow;ctx.fillRect(px,py,T,T);ctx.restore();
    ctx.fillStyle='rgba(0,0,0,.25)';ctx.fillRect(px,py+T-5,T,5);ctx.fillRect(px+T-5,py,5,T);ctx.fillStyle='rgba(255,255,255,.6)';ctx.fillRect(px,py,T,4);ctx.fillRect(px,py,4,T);
    ctx.fillStyle='#3a2600';const q=[[1,0],[2,0],[3,0],[0,1],[4,1],[4,2],[3,3],[2,4],[2,6]];for(const[a,b]of q)ctx.fillRect(px+8+a*4,py+5+b*4,4,4);break }
  case 8: ctx.fillStyle='#4a4560';ctx.fillRect(px,py,T,T);ctx.fillStyle='rgba(0,0,0,.3)';ctx.fillRect(px,py+T-4,T,4);ctx.fillRect(px+T-4,py,4,T);break;
  case 9: { const a=.45+.25*Math.sin(time*6+y);ctx.fillStyle=`rgba(255,110,220,${a})`;ctx.fillRect(px+6,py,T-12,T);ctx.fillStyle='rgba(255,230,250,.85)';ctx.fillRect(px+15,py,6,T);break }
  case 10: ctx.fillStyle=w.plank;ctx.fillRect(px,py,T,T);ctx.fillStyle=w.plank2;ctx.fillRect(px,py+11,T,3);ctx.fillRect(px,py+24,T,3);ctx.fillRect(px+((x%2)?8:24),py,3,11);ctx.fillStyle='rgba(255,255,255,.18)';ctx.fillRect(px,py,T,3);break;
  case 11: { ctx.save();ctx.shadowColor=w.glow;ctx.shadowBlur=14+6*Math.sin(time*3+x);ctx.fillStyle='#3b2a12';ctx.fillRect(px,py,T,T);ctx.restore();ctx.fillStyle=w.glow;
    [[4,4],[18,6],[10,16],[24,20],[6,26],[20,28]].forEach(([a,b],i)=>{ctx.globalAlpha=.65+.35*Math.sin(time*4+i+x);ctx.fillRect(px+a,py+b,8,6)});ctx.globalAlpha=1;break }
  }
}
function dots(px,py,col,hs,n,y0){ctx.fillStyle=col;for(let i=0;i<n;i++){const a=hash(px+i,py-i);ctx.fillRect(px+(a*5|0)*6+3,py+y0+((hash(py+i,px)*(T-y0-6)/6)|0)*6+3,5,5)}}
function drawDeco(d,w){
  const px=d.x*T,gy=d.y*T;
  if(S.world===0){ // cypress tree + moss
    const h=3+(d.s*3|0);ctx.fillStyle='#5b4330';ctx.fillRect(px+10,gy-h*T,16,h*T);ctx.fillRect(px+2,gy-14,32,14);
    ctx.fillStyle='#2f6b3a';ctx.fillRect(px-26,gy-h*T-40,88,44);ctx.fillRect(px-10,gy-h*T-70,56,32);
    ctx.fillStyle='rgba(190,205,170,.8)';ctx.fillRect(px-18,gy-h*T+4,6,30);ctx.fillRect(px+46,gy-h*T+4,6,42);
    if(d.k===1){ctx.fillStyle='#c9a46a';ctx.fillRect(px+40,gy-12,16,12);ctx.fillStyle='#8c6a3a';ctx.fillRect(px+43,gy-10,10,3)} // shell
  }else if(S.world===1){
    if(d.k===0){ const h=3+(d.s*2|0);ctx.fillStyle='#7a4f2c';ctx.fillRect(px+10,gy-h*T,16,h*T);ctx.fillStyle='#3e9e3a';ctx.fillRect(px-26,gy-h*T-56,88,62);ctx.fillStyle='#57bf4a';ctx.fillRect(px-14,gy-h*T-76,64,26);
      ctx.fillStyle='#8a5a33';ctx.fillRect(px-4,gy-6,10,6);ctx.fillRect(px+30,gy-6,10,6) }
    else { // big flower: stem, leaves, petals, seeds
      ctx.fillStyle='#2f9a35';ctx.fillRect(px+16,gy-80,6,80);ctx.fillRect(px+22,gy-46,16,8);ctx.fillRect(px,gy-30,16,8);
      const pc=d.k===1?'#ff7ab8':'#ffd23f';ctx.fillStyle=pc;ctx.fillRect(px+4,gy-104,30,10);ctx.fillRect(px+14,gy-114,10,30);ctx.fillStyle='#6b3e12';ctx.fillRect(px+13,gy-103,12,8) }
  }else{
    // cell decorations: mitochondria bean, nucleus blob on stalk, chloroplast
    if(d.k===0){ctx.fillStyle='rgba(255,140,90,.7)';ctx.fillRect(px,gy-30,44,18);ctx.fillRect(px+6,gy-36,32,30);ctx.fillStyle='rgba(255,220,180,.7)';ctx.fillRect(px+6,gy-24,32,3);}
    else if(d.k===1){ctx.fillStyle='rgba(120,220,140,.65)';ctx.fillRect(px,gy-22,34,16);ctx.fillStyle='rgba(40,140,60,.8)';for(let i=0;i<3;i++)ctx.fillRect(px+5+i*9,gy-19,5,10)}
    else{ glowRect(px+8,gy-40,22,22,'rgba(110,240,255,.8)',12);ctx.fillStyle='#1d5f7a';ctx.fillRect(px+15,gy-33,8,8)}
  }
}
function drawFlag(x,y,on,w){ctx.fillStyle='#ddd';ctx.fillRect(x-2,y-70,4,70);ctx.fillStyle=on?w.glow:'#777';if(on){ctx.save();ctx.shadowColor=w.glow;ctx.shadowBlur=12}ctx.fillRect(x+2,y-70,26,18);if(on)ctx.restore()}
function drawCrystal(c,w){
  const bob=Math.sin(time*3+c.x)*3,x=c.x,y=c.y-6+bob;
  if(c.ready){ctx.save();ctx.shadowColor=w.glow;ctx.shadowBlur=26+10*Math.sin(time*6);}
  ctx.fillStyle=c.ready?w.glow:'#555';
  ctx.fillRect(x-6,y-44,12,44);ctx.fillRect(x-12,y-34,24,24);ctx.fillRect(x-3,y-52,6,10);
  if(c.ready)ctx.restore();
  ctx.fillStyle='rgba(255,255,255,.7)';ctx.fillRect(x-4,y-40,4,18);
  if(c.ready){ctx.fillStyle='#fff';ctx.font='700 12px Silkscreen, monospace';ctx.textAlign='center';ctx.fillText('TOUCH',x,y-62)}
}
function drawMob(m,w){
  const x=m.x,y=m.y,f=m.vx>0?1:-1,leg=Math.sin(m.t*12)*3;
  if(w.mob==='crawfish'){ctx.fillStyle='#c8432f';ctx.fillRect(x+4,y+6,22,14);ctx.fillRect(x+(f>0?24:-4),y+2,10,8);ctx.fillRect(x+(f>0?24:-4),y+12,10,6);ctx.fillStyle='#8f2a1d';ctx.fillRect(x+8,y+6,3,14);ctx.fillRect(x+15,y+6,3,14);ctx.fillRect(x+4,y+20,4,4+leg);ctx.fillRect(x+20,y+20,4,4-leg);ctx.fillStyle='#1b1006';ctx.fillRect(x+(f>0?20:8),y+4,4,4)}
  else if(w.mob==='beetle'){ctx.fillStyle='#2d3fa8';ctx.fillRect(x+3,y+4,24,16);ctx.fillStyle='#4f66e0';ctx.fillRect(x+3,y+4,24,4);ctx.fillStyle='#111';ctx.fillRect(x+14,y+4,2,16);ctx.fillRect(x+(f>0?26:-2),y+8,6,8);ctx.fillRect(x+5,y+20,3,4+leg);ctx.fillRect(x+21,y+20,3,4-leg);ctx.fillStyle='#5a3a1a';ctx.fillRect(x+(f>0?28:-1),y+10,2,2)}
  else{const b=Math.sin(m.t*5)*2;ctx.save();ctx.shadowColor='#9dff6e';ctx.shadowBlur=10;ctx.fillStyle='#6fd64a';ctx.fillRect(x+2,y+4+b,26,18);ctx.fillRect(x+6,y+b,18,26);ctx.restore();ctx.fillStyle='#3a8f2a';[[0,8],[26,10],[12,-4],[10,24]].forEach(([a,c])=>ctx.fillRect(x+a,y+c+b,4,4));ctx.fillStyle='#fff';ctx.fillRect(x+9,y+8+b,6,6);ctx.fillRect(x+17,y+8+b,6,6);ctx.fillStyle='#3b2412';ctx.fillRect(x+11,y+10+b,3,3);ctx.fillRect(x+19,y+10+b,3,3)}
}
function drawPlayer(p){
  const x=Math.round(p.x),y=Math.round(p.y),f=p.face,leg=p.ground?Math.sin(p.walk)*5:3;
  // legs
  ctx.fillStyle='#2b3a67';ctx.fillRect(x+5,y+32,7,12+(p.ground?leg:-2));ctx.fillRect(x+14,y+32,7,12-(p.ground?leg:-2));
  ctx.fillStyle='#3a2414';ctx.fillRect(x+4,y+42+(p.ground?leg:-2),9,4);ctx.fillRect(x+13,y+42-(p.ground?leg:-2),9,4);
  // lab coat body
  ctx.fillStyle='#f4f4f4';ctx.fillRect(x+2,y+16,22,18);ctx.fillStyle='#1fa6a0';ctx.fillRect(x+9,y+16,8,14);
  ctx.fillStyle='#f4f4f4';ctx.fillRect(x+(f>0?20:-2),y+18+(p.ground?-leg/2:0),6,12);
  // head
  ctx.fillStyle='#8d5a3b';ctx.fillRect(x+3,y,20,17);
  ctx.fillStyle='#2b1a10';ctx.fillRect(x+3,y,20,5);ctx.fillRect(x+(f>0?3:19),y,4,10);
  // goggles on forehead
  ctx.fillStyle='#6ef0ff';ctx.fillRect(x+6,y+4,6,3);ctx.fillRect(x+14,y+4,6,3);
  // eyes: brown iris, dark pupil
  const ex=f>0?2:-2;ctx.fillStyle='#fff';ctx.fillRect(x+7+ex,y+8,5,4);ctx.fillRect(x+15+ex,y+8,5,4);
  ctx.fillStyle='#5a3418';ctx.fillRect(x+9+ex,y+8,3,4);ctx.fillRect(x+17+ex,y+8,3,4);
  ctx.fillStyle='#5a2e1e';ctx.fillRect(x+10+ex,y+13,6,2);
}
function drawDragon(B,k,dying){
  const x=B.x,y=B.y,f=B.face,t=time,flap=Math.sin(t*6)*1;
  const pal=[
    {body:'#5f7a3a',belly:'#c9b27a',plate:'#a8834d',bone:'#ffd75e',wing:'#3f5a2a'},
    {body:'#2f8f3a',belly:'#a5e07a',plate:'#7a3d1c',bone:'#c6ff5e',wing:'#4fbf4a'},
    {body:'rgba(150,90,220,.82)',belly:'rgba(220,190,255,.8)',plate:'#e06fd0',bone:'#6ef0ff',wing:'rgba(120,70,200,.7)'}][k];
  ctx.save();
  if(dying){ctx.globalAlpha=.4+.3*Math.sin(t*30)}
  ctx.translate(x,y);ctx.scale(f*1.2,1.2);
  if(B.flash>0&&Math.floor(t*20)%2){ctx.filter='brightness(2.2)'}
  // tail
  for(let i=0;i<7;i++){const tx=-60-i*18,ty=Math.sin(t*3-i*.7)*8+i*3,s=22-i*2.4;ctx.fillStyle=pal.body;ctx.fillRect(tx-s/2,ty-s/2,s,s);ctx.fillStyle=pal.bone;ctx.fillRect(tx-2,ty-2,4,4)}
  if(k===1){ctx.fillStyle=pal.plate;ctx.fillRect(-60-7*18-6,Math.sin(t*3-4.9)*8+18,14,14)}
  // back wing
  ctx.fillStyle=pal.wing;const wy=-30-flap*26;
  for(let i=0;i<4;i++)ctx.fillRect(-36+i*14,wy+i*8,16,(36-wy)-i*8-20);
  // body
  ctx.fillStyle=pal.body;ctx.fillRect(-64,-26,124,56);
  ctx.fillStyle=pal.belly;ctx.fillRect(-52,16,100,14);
  // endoskeleton: glowing spine + ribs
  ctx.save();ctx.shadowColor=pal.bone;ctx.shadowBlur=16;ctx.fillStyle=pal.bone;
  ctx.fillRect(-58,-14,112,5);for(let i=0;i<6;i++)ctx.fillRect(-48+i*18,-10,5,22);ctx.restore();
  // themed armor
  if(k===0){ctx.fillStyle=pal.plate;for(let i=0;i<5;i++){ctx.fillRect(-56+i*22,-40,20,14);ctx.fillStyle='#7d5f33';ctx.fillRect(-56+i*22,-30,20,4);ctx.fillStyle=pal.plate}}
  if(k===1){ctx.fillStyle=pal.plate;for(let i=0;i<6;i++){ctx.fillRect(-54+i*19,-36,8,10);ctx.fillRect(-52+i*19,-44,4,8)}ctx.fillStyle='#ff7ab8';ctx.fillRect(-10,-50,12,8);ctx.fillStyle='#ffd23f';ctx.fillRect(-7,-48,6,4)}
  if(k===2){ctx.save();ctx.shadowColor='#ff7ad9';ctx.shadowBlur=22;ctx.fillStyle='#ff7ad9';ctx.fillRect(-18,-8,34,30);ctx.restore();ctx.fillStyle='#9a2f88';ctx.fillRect(-8,0,14,14);
    ctx.strokeStyle='rgba(230,200,255,.9)';ctx.lineWidth=3;ctx.strokeRect(-66,-28,128,60)}
  // legs
  ctx.fillStyle=pal.body;ctx.fillRect(-46,30,16,16);ctx.fillRect(28,30,16,16);ctx.fillStyle='#2a2a2a';ctx.fillRect(-48,44,6,5);ctx.fillRect(-36,44,6,5);ctx.fillRect(26,44,6,5);ctx.fillRect(38,44,6,5);
  // neck + head
  ctx.fillStyle=pal.body;ctx.fillRect(54,-34,26,30);ctx.fillRect(70,-56,50,40);ctx.fillRect(116,-44,26,22);
  ctx.fillStyle=pal.belly;ctx.fillRect(116,-26,26,6);
  ctx.fillStyle=pal.plate;ctx.fillRect(76,-68,8,14);ctx.fillRect(96,-70,8,16);
  // eye: brown iris + black pupil
  ctx.fillStyle='#fff6e0';ctx.fillRect(100,-48,14,12);ctx.fillStyle='#6b3a16';ctx.fillRect(106,-48,8,12);ctx.fillStyle='#120a04';ctx.fillRect(109,-46,4,8);
  ctx.fillStyle='#1a1a1a';ctx.fillRect(136,-40,4,4);
  // front wing
  ctx.fillStyle=pal.wing;ctx.globalAlpha*=.92;const fw=-40-flap*34;
  for(let i=0;i<5;i++)ctx.fillRect(-20+i*14,fw+i*9,16,(-10-fw)-i*9);
  ctx.fillStyle=pal.bone;for(let i=0;i<5;i++)ctx.fillRect(-20+i*14,fw+i*9,16,3);
  ctx.restore();
}
function drawHUD(w){
  // top bar
  ctx.fillStyle='rgba(10,8,22,.62)';ctx.fillRect(0,0,VW,46);
  for(let i=0;i<S.maxHearts;i++)heart(14+i*30,12,i<S.hearts);
  ctx.font='700 15px Silkscreen, monospace';ctx.textBaseline='middle';ctx.textAlign='left';
  glowRect(174,15,12,16,w.glow,8);ctx.fillStyle='#fff';ctx.fillText('x'+S.gems,192,23);
  // code slots
  ctx.textAlign='center';ctx.fillStyle='#b4acd6';ctx.font='700 11px Silkscreen, monospace';ctx.fillText('CODE',290,23);
  for(let i=0;i<9;i++){const x=320+i*24;ctx.fillStyle=i<S.letters.length?w.glow:'rgba(255,255,255,.18)';ctx.fillRect(x,10,20,26);ctx.fillStyle=i<S.letters.length?'#2a1a00':'#fff';ctx.font='700 16px Silkscreen, monospace';ctx.fillText(S.letters[i]||'',x+10,24)}
  ctx.textAlign='left';ctx.fillStyle='#fff';ctx.font='700 13px Silkscreen, monospace';
  const done=L.qb.filter(q=>q.done).length;
  ctx.fillText(`${w.name}  ?${done}/3`,560,23);
  // boss bar
  const B=L.boss;
  if(B&&!L.bossDone){const bw=420,bx=(VW-bw)/2,by=VH-40;ctx.fillStyle='rgba(10,8,22,.75)';ctx.fillRect(bx-8,by-24,bw+16,44);ctx.fillStyle='#fff';ctx.textAlign='center';ctx.font='700 13px Silkscreen, monospace';ctx.fillText(w.boss,VW/2,by-11);
    ctx.fillStyle='#3b0f22';ctx.fillRect(bx,by,bw,12);ctx.fillStyle='#ff5a8a';ctx.fillRect(bx,by,bw*B.hp/B.max,12);for(let i=1;i<B.max;i++){ctx.fillStyle='#000';ctx.fillRect(bx+bw*i/B.max-1,by,2,12)}}
  // toasts
  toasts.forEach((t,i)=>{ctx.globalAlpha=Math.min(1,t.life*2);ctx.font='700 18px Silkscreen, monospace';ctx.textAlign='center';const tw=ctx.measureText(t.t).width+28;ctx.fillStyle='rgba(10,8,22,.8)';ctx.fillRect(VW/2-tw/2,62+i*38,tw,32);ctx.fillStyle=t.c;ctx.fillText(t.t,VW/2,79+i*38)});ctx.globalAlpha=1;
  // hint near q block
  if(S.mode==='play'&&P){const cx=P.x+P.w/2;for(const b of L.qb){if(b.done)continue;const bx=b.tx*T+T/2;if(Math.abs(bx-cx)<T*1.6&&Math.abs(b.ty*T-P.y)<T*3){ctx.font='700 13px Silkscreen, monospace';ctx.textAlign='center';ctx.fillStyle='#fff';ctx.fillText('Jump into it or press E',bx-cam,b.ty*T-14)}}}
}
function heart(x,y,full){const c=full?'#ff4f6d':'rgba(255,255,255,.2)';ctx.fillStyle=c;[[1,0],[2,0],[4,0],[5,0],[0,1],[1,1],[2,1],[3,1],[4,1],[5,1],[6,1],[0,2],[1,2],[2,2],[3,2],[4,2],[5,2],[6,2],[1,3],[2,3],[3,3],[4,3],[5,3],[2,4],[3,4],[4,4],[3,5]].forEach(([a,b])=>ctx.fillRect(x+a*3.4,y+b*3.4,3.4,3.4))}

/* ---------- LOOP ---------- */
let last=performance.now();
function loop(now){
  const dt=Math.min(1/30,(now-last)/1000);last=now;time+=dt;
  if(S.mode==='play'&&L)update(dt);
  updateFx(dt);
  draw();
  requestAnimationFrame(loop);
}
// title backdrop level
L=buildLevel(0);P=newPlayer(8*T,L.gy[8]*T);cam=0;
titleScreen();
requestAnimationFrame(loop);
})();
</script>

</body>
</html>
