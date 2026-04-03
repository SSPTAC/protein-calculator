# protein-calculator

<!DOCTYPE html>

<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Protein Calculator</title>
<style>
body{font-family:Arial,sans-serif;background:#fff;color:#111;margin:0;padding:20px}
.wrap{max-width:600px;margin:0 auto}
h1{font-size:28px;margin-bottom:8px}
h1 span{color:#f97316}
p{color:#444;margin-bottom:24px;line-height:1.5}
.q{display:none}
.q.on{display:block}
.ql{font-size:11px;text-transform:uppercase;letter-spacing:.1em;color:#f97316;font-weight:700;margin-bottom:8px}
.qt{font-size:22px;font-weight:700;margin-bottom:20px}
.opt{display:flex;align-items:center;gap:12px;border:2px solid #ddd;padding:14px;margin-bottom:10px;cursor:pointer;background:#f9f9f9}
.opt:hover{border-color:#f97316}
.opt.sel{border-color:#f97316;background:#fff7f0}
.opt span{font-size:16px;font-weight:500}
.opt small{display:block;color:#666;font-size:13px}
.nw{display:flex;align-items:center;gap:0;border:2px solid #ddd;width:200px}
.nb{width:50px;height:56px;background:#eee;border:none;font-size:24px;cursor:pointer}
.nb:hover{background:#f97316;color:#fff}
.ni{width:80px;height:56px;border:none;font-size:28px;font-weight:700;text-align:center;outline:none}
.nu{padding:0 12px;font-size:13px;color:#666}
.nav{margin-top:24px;display:flex;gap:10px}
.btn{background:#f97316;color:#fff;border:none;padding:14px 28px;font-size:16px;font-weight:700;cursor:pointer;flex:1}
.btn:hover{background:#e06610}
.btn:disabled{background:#ccc;cursor:not-allowed}
.bbk{background:#fff;color:#666;border:2px solid #ddd;padding:14px 20px;font-size:16px;cursor:pointer}
.bbk:hover{border-color:#111;color:#111}
#result{display:none}
.rbox{background:#f9f9f9;border:2px solid #ddd;padding:24px;margin-bottom:16px}
.rl{font-size:11px;text-transform:uppercase;letter-spacing:.1em;color:#f97316;font-weight:700}
.rn{font-size:80px;font-weight:900;line-height:1;color:#111}
.rn span{font-size:32px;color:#f97316}
.rs{color:#555;margin-top:8px;line-height:1.5}
.mrow{display:flex;gap:12px;padding:12px 0;border-bottom:1px solid #ddd;align-items:flex-start}
.mrow:last-child{border:none}
.mp{font-size:22px;font-weight:900;color:#f97316;min-width:56px}
.mp small{font-size:12px;color:#666;font-weight:400;display:block}
.mn{font-size:14px;font-weight:600;margin-bottom:2px}
.md{font-size:12px;color:#666}
.tag{font-size:10px;font-weight:700;text-transform:uppercase;background:#fff0e6;color:#f97316;padding:2px 6px;flex-shrink:0}
.cta{background:#f97316;padding:24px;text-align:center;margin-bottom:16px}
.cta h2{color:#111;font-size:22px;margin-bottom:8px}
.cta p{color:rgba(0,0,0,.7);margin-bottom:16px}
.cta input{width:100%;padding:12px;font-size:15px;border:none;margin-bottom:8px;box-sizing:border-box}
.csub{width:100%;background:#111;color:#fff;border:none;padding:14px;font-size:16px;font-weight:700;cursor:pointer}
.csub:hover{background:#333}
.fine{font-size:11px;color:rgba(0,0,0,.5);margin-top:8px}
.thanks{display:none;font-size:20px;font-weight:700;color:#111;margin-top:12px}
.restart{text-align:center;margin-top:12px}
.restart button{background:none;border:none;color:#888;font-size:13px;cursor:pointer;text-decoration:underline}
</style>
</head>
<body>
<div class="wrap">
<div id="hdr">
<h1>YOUR <span>PROTEIN</span> TARGET IN 60 SECONDS</h1>
<p>Built for tradies and hardworking people over 30 who want to get lean and strong without living in the kitchen.</p>
</div>

<div class="q on" id="q0">
<div class="ql">Question 1 of 4</div>
<div class="qt">What is your current weight?</div>
<div class="nw">
<button class="nb" id="wdn">-</button>
<input class="ni" type="number" id="wt" value="85" min="50" max="180">
<span class="nu">KG</span>
<button class="nb" id="wup">+</button>
</div>
<div class="nav"><button class="btn" id="n0">NEXT</button></div>
</div>

<div class="q" id="q1">
<div class="ql">Question 2 of 4</div>
<div class="qt">What is your main goal?</div>
<div class="opt" data-k="goal" data-v="lose-fat"><span>Lose fat, keep my strength<small>Drop the gut without losing muscle</small></span></div>
<div class="opt" data-k="goal" data-v="build"><span>Build muscle and get stronger<small>Add size and feel more capable</small></span></div>
<div class="opt" data-k="goal" data-v="recomp"><span>Get lean and more energetic<small>Look and feel better overall</small></span></div>
<div class="nav"><button class="bbk" id="b1">BACK</button><button class="btn" id="n1" disabled>NEXT</button></div>
</div>

<div class="q" id="q2">
<div class="ql">Question 3 of 4</div>
<div class="qt">What does your work day look like?</div>
<div class="opt" data-k="work" data-v="heavy"><span>Heavy physical work all day<small>Concreting, roofing, demolition, labouring</small></span></div>
<div class="opt" data-k="work" data-v="moderate"><span>Moderate physical work<small>Plumbing, electrical, carpentry, landscaping</small></span></div>
<div class="opt" data-k="work" data-v="light"><span>Mostly sitting at a desk<small>Office, admin, project management</small></span></div>
<div class="nav"><button class="bbk" id="b2">BACK</button><button class="btn" id="n2" disabled>NEXT</button></div>
</div>

<div class="q" id="q3">
<div class="ql">Question 4 of 4</div>
<div class="qt">How often do you train right now?</div>
<div class="opt" data-k="training" data-v="none"><span>Barely at all<small>Maybe once a week or less</small></span></div>
<div class="opt" data-k="training" data-v="some"><span>A couple of times a week<small>Trying to be consistent</small></span></div>
<div class="opt" data-k="training" data-v="regular"><span>3-5 times a week<small>Training is already part of my routine</small></span></div>
<div class="nav"><button class="bbk" id="b3">BACK</button><button class="btn" id="n3" disabled>GET MY TARGET</button></div>
</div>

<div id="result">
<div class="rbox">
<div class="rl">Your daily protein target</div>
<div class="rn" id="rnum">160 <span>g</span></div>
<div class="rs" id="rsub"></div>
</div>
<div class="rbox">
<strong style="font-size:16px;display:block;margin-bottom:14px">HOW TO HIT IT ON A WORKDAY</strong>
<div id="meals"></div>
</div>
<div class="cta">
<h2>Want a full week of meals built around your target?</h2>
<p>Drop your email and I will send you 7 days of meals matched to your exact protein number -- no chef required.</p>
<input type="text" id="fn" placeholder="Your first name">
<input type="email" id="fe" placeholder="Your best email address">
<button class="csub" id="sb">SEND ME MY MEAL WEEK</button>
<div class="fine">No spam. Just the meals. Unsubscribe any time.</div>
<div class="thanks" id="tk">You are in. Check your inbox.</div>
</div>
<div class="restart"><button id="rs">Recalculate for different stats</button></div>
</div>
</div>
<script>
var a={goal:null,work:null,training:null};
document.getElementById('wdn').onclick=function(){var i=document.getElementById('wt');i.value=Math.max(50,parseInt(i.value)-1);};
document.getElementById('wup').onclick=function(){var i=document.getElementById('wt');i.value=Math.min(180,parseInt(i.value)+1);};
document.getElementById('n0').onclick=function(){go(1);};
document.getElementById('b1').onclick=function(){go(0);};
document.getElementById('n1').onclick=function(){go(2);};
document.getElementById('b2').onclick=function(){go(1);};
document.getElementById('n2').onclick=function(){go(3);};
document.getElementById('b3').onclick=function(){go(2);};
document.getElementById('n3').onclick=function(){show();};
document.getElementById('sb').onclick=function(){sub();};
document.getElementById('rs').onclick=function(){reset();};
document.querySelectorAll('.opt').forEach(function(el){
  el.onclick=function(){
    var k=el.getAttribute('data-k'),v=el.getAttribute('data-v');
    a[k]=v;
    el.closest('.q').querySelectorAll('.opt').forEach(function(o){o.classList.remove('sel');});
    el.classList.add('sel');
    var m={goal:'n1',work:'n2',training:'n3'};
    document.getElementById(m[k]).disabled=false;
  };
});
function go(s){
  document.querySelectorAll('.q').forEach(function(b,i){b.classList.toggle('on',i===s);});
}
function calc(){
  var w=parseInt(document.getElementById('wt').value)||85,m=2.0;
  if(a.goal==='lose-fat')m=2.2;
  else if(a.goal==='recomp')m=2.1;
  if(a.work==='heavy')m+=0.1;
  else if(a.work==='light')m-=0.1;
  if(a.training==='regular')m+=0.1;
  else if(a.training==='none')m-=0.1;
  return Math.round(w*m);
}
function show(){
  var t=calc(),w=a.work;
  document.getElementById('rnum').innerHTML=t+' <span>g</span>';
  var ctx='This target keeps you lean, energetic, and recovering properly.';
  if(a.goal==='lose-fat'&&w==='heavy')ctx='You do heavy work on top of training. You need more protein than most to hold muscle while losing fat.';
  else if(a.goal==='lose-fat')ctx='Higher protein keeps you full, preserves muscle while you cut, and stops energy crashes during long work days.';
  else if(a.goal==='build')ctx='Building muscle on top of a physical job means more stress. Hitting this number is non-negotiable for recovery.';
  document.getElementById('rsub').textContent=ctx;
  var q1=Math.round(t*.25),q2=Math.round(t*.30),q3=Math.round(t*.25),q4=Math.round(t*.20);
  var bf=w==='light'?'4 eggs + 2 slices toast':'4 eggs + 200g Greek yoghurt';
  var ln=w!=='light'?'Tuna + crackers + boiled eggs from servo':'Chicken wrap or tuna salad';
  var ms=[
    {p:q1,n:bf,d:'Before leaving home',tag:'Breakfast'},
    {p:q2,n:ln,d:w!=='light'?'No cooking needed':'Packed the night before',tag:w!=='light'?'Site Lunch':'Desk Lunch'},
    {p:q3,n:'200g chicken or mince with rice',d:'Batch cooked Sunday -- reheat in 3 minutes',tag:'Dinner'},
    {p:q4,n:'250g cottage cheese or protein shake',d:'Before bed or arvo snack',tag:'Snack'}
  ];
  document.getElementById('meals').innerHTML=ms.map(function(m){
    return '<div class="mrow"><div class="mp">'+m.p+'<small>g protein</small></div><div><div class="mn">'+m.n+'</div><div class="md">'+m.d+'</div></div><div class="tag">'+m.tag+'</div></div>';
  }).join('');
  document.querySelectorAll('.q').forEach(function(b){b.classList.remove('on');});
  document.getElementById('hdr').style.display='none';
  document.getElementById('result').style.display='block';
  window.scrollTo(0,0);
}
function sub(){
  var n=document.getElementById('fn').value.trim(),e=document.getElementById('fe').value.trim();
  if(!n||!e){alert('Please enter your name and email.');return;}
  var d=new FormData();
  d.append('fields[name]',n);d.append('fields[email]',e);d.append('ml-submit','1');d.append('anticsrf','true');
  fetch('https://assets.mailerlite.com/jsonp/2149578/forms/183718325525677235/subscribe',{method:'POST',body:d,mode:'no-cors'});
  document.getElementById('fn').style.display='none';
  document.getElementById('fe').style.display='none';
  document.getElementById('sb').style.display='none';
  document.getElementById('tk').style.display='block';
}
function reset(){
  a={goal:null,work:null,training:null};
  document.getElementById('result').style.display='none';
  document.getElementById('hdr').style.display='block';
  document.querySelectorAll('.opt').forEach(function(o){o.classList.remove('sel');});
  ['n1','n2','n3'].forEach(function(id){document.getElementById(id).disabled=true;});
  ['fn','fe','sb'].forEach(function(id){document.getElementById(id).style.display='';});
  document.getElementById('tk').style.display='none';
  go(0);
}
</script>
</body>
</html>
