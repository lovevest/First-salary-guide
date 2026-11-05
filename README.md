<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>First Salary Guide</title>
<style>
:root{--bg:#f6f7fb;--card:#fff;--tx:#1b1e2e;--mut:#6b7185;--bd:#e3e6f0;--pri:#4f46e5;--pri-tx:#fff;--g1:#4f46e5;--g2:#f59e0b;--g3:#10b981;--warn:#fff7e6;--warn-tx:#8a5a00;
box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){color-scheme:dark;--bg:#12141f;--card:#1b1e2e;--tx:#eef0fa;--mut:#9aa1ba;--bd:#2c3044;--pri:#818cf8;--pri-tx:#12141f;--warn:#2d2410;--warn-tx:#f5c96a}}
:root[data-theme="dark"]{color-scheme:dark;--bg:#12141f;--card:#1b1e2e;--tx:#eef0fa;--mut:#9aa1ba;--bd:#2c3044;--pri:#818cf8;--pri-tx:#12141f;--warn:#2d2410;--warn-tx:#f5c96a}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--tx);font-family:"Noto Sans Thai",-apple-system,"Segoe UI",sans-serif;line-height:1.6}
main{max-width:560px;margin:0 auto;padding:16px 16px 40px}
h1{font-size:22px;margin:8px 0 2px}h2{font-size:17px;margin:0 0 10px}
.sub{color:var(--mut);font-size:14px;margin:0 0 16px}
.card{background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:16px;margin-bottom:14px}
label{display:block;font-size:14px;font-weight:600;margin:10px 0 4px}
input[type=number]{width:100%;font-size:16px;padding:12px;border:1px solid var(--bd);border-radius:10px;background:var(--bg);color:var(--tx)}
input[type=range]{width:100%;accent-color:var(--pri)}
.err{color:#d93a3a;font-size:13px;min-height:18px}
.bar{display:flex;height:22px;border-radius:11px;overflow:hidden;margin:12px 0}
.bar div{transition:width .15s}
.row{display:flex;justify-content:space-between;align-items:center;font-size:14px;margin:6px 0;gap:12px}
.dot{display:inline-block;width:10px;height:10px;border-radius:50%;margin-right:6px}
.big{font-weight:700;text-align:right;flex:0 0 auto}
.note{font-size:13px;color:var(--mut)}
.stage{display:flex;gap:12px;padding:12px 0;border-top:1px solid var(--bd)}
.stage:first-of-type{border-top:0}
.num{flex:0 0 32px;height:32px;border-radius:50%;background:var(--bd);display:flex;align-items:center;justify-content:center;font-weight:700;font-size:14px}
.stage.done .num{background:var(--g3);color:#fff}
.stage.cur .num{background:var(--pri);color:var(--pri-tx)}
.stage.lock{opacity:.5}
.stage b{display:block}
.stage p{margin:2px 0 8px;font-size:13px;color:var(--mut)}
button{font:inherit;font-size:14px;font-weight:600;padding:10px 14px;border-radius:10px;border:0;background:var(--pri);color:var(--pri-tx);cursor:pointer}
button.ghost{background:transparent;color:var(--mut);border:1px solid var(--bd)}
.warn{background:var(--warn);color:var(--warn-tx);border-radius:12px;padding:10px 12px;font-size:13px}
.risk{display:flex;gap:8px;align-items:flex-start;font-size:13px;margin:4px 0}
.tag{font-size:12px;padding:1px 8px;border-radius:8px;color:#fff;flex:0 0 auto}
.chk{display:flex;gap:10px;align-items:flex-start;font-size:14px;font-weight:400;margin:8px 0}
.chk input{margin-top:5px;width:18px;height:18px;accent-color:var(--pri);flex:0 0 auto}
</style>
</head>
<body>
<main>
<h1>First Salary Guide</h1>
<p class="sub">เงินเดือนแรก ไปต่อทีละก้าว ตั้งแต่เงินสำรองถึงลงทุนก้อนแรก</p>

<section class="card">
<h2>ด่าน 1 · รู้รายรับรายจ่าย</h2>
<label for="sal">เงินเดือนสุทธิต่อเดือน (บาท)</label>
<input id="sal" type="number" inputmode="numeric" min="0" placeholder="เช่น 20000">
<label for="exp">ค่าใช้จ่ายจำเป็นต่อเดือน (บาท)</label>
<input id="exp" type="number" inputmode="numeric" min="0" placeholder="เช่น 9000">
<div class="err" id="err"></div>
</section>

<section class="card" id="split">
<h2>ด่าน 2 · แบ่งเงินเป็นก้อน</h2>
<p class="note" style="margin-top:0">เริ่มต้นที่กฎ 50/30/20 แล้วลากปรับได้ตามชีวิตจริง</p>
<label for="sn">จำเป็น <span id="pn"></span></label>
<input id="sn" type="range" min="0" max="100" step="1" value="50">
<label for="sw">อยากได้และไลฟ์สไตล์ <span id="pw"></span></label>
<input id="sw" type="range" min="0" max="100" step="1" value="30">
<div class="bar"><div id="b1" style="background:var(--g1)"></div><div id="b2" style="background:var(--g2)"></div><div id="b3" style="background:var(--g3)"></div></div>
<div class="row"><span><i class="dot" style="background:var(--g1)"></i>จำเป็น</span><span class="big" id="v1"></span></div>
<div class="row"><span><i class="dot" style="background:var(--g2)"></i>ไลฟ์สไตล์</span><span class="big" id="v2"></span></div>
<div class="row"><span><i class="dot" style="background:var(--g3)"></i>ออมและลงทุน</span><span class="big" id="v3"></span></div>
<div id="future" style="margin-top:10px"></div>
</section>

<section class="card">
<h2>เส้นทาง 5 ด่าน</h2>
<div id="stages"></div>
<button class="ghost" id="reset" style="margin-top:8px">เริ่มใหม่</button>
</section>

<section class="card">
<h2>โบนัส · สวัสดิการ ประกัน PVD และภาษี</h2>
<p class="note" style="margin-top:0">เช็กสิทธิที่มักมองข้ามเมื่อเริ่มทำงาน ติ๊กเมื่อเช็กแล้ว</p>
<label class="chk"><input type="checkbox" data-c="0"><span>ประกันสังคม: ถูกหักจากเงินเดือนอัตโนมัติ ตรวจสิทธิรักษาพยาบาลและเงินกรณีว่างงาน</span></label>
<label class="chk"><input type="checkbox" data-c="1"><span>สวัสดิการบริษัท: ถามฝ่ายบุคคลเรื่องประกันกลุ่ม ค่ารักษา และวันลา</span></label>
<label class="chk"><input type="checkbox" data-c="2"><span>PVD (กองทุนสำรองเลี้ยงชีพ): ถามว่าบริษัทสมทบเท่าไร ถ้าสมทบให้ ควรสะสมอย่างน้อยเท่าที่บริษัทสมทบ</span></label>
<label class="chk"><input type="checkbox" data-c="3"><span>ประกันส่วนตัว: ซื้อเมื่อมีเงินสำรองฉุกเฉินแล้ว เน้นประกันสุขภาพและอุบัติเหตุก่อน อย่าซื้อเพราะถูกเชียร์</span></label>
<h2 style="margin-top:16px">ประมาณภาษีและค่าลดหย่อน</h2>
<label for="pvd">เงินสะสม PVD ต่อเดือน (บาท)</label>
<input id="pvd" type="number" inputmode="numeric" min="0" placeholder="เช่น 1000 (ไม่มีให้เว้นว่าง)">
<label for="ins">เบี้ยประกันชีวิตและสุขภาพต่อปี (บาท)</label>
<input id="ins" type="number" inputmode="numeric" min="0" placeholder="เช่น 12000 (ไม่มีให้เว้นว่าง)">
<div id="taxout" style="margin-top:10px"></div>
</section>

<div class="warn">ข้อมูลทั่วไปเพื่อการเรียนรู้ ไม่ใช่คำแนะนำทางการเงินส่วนบุคคล ผลตอบแทนในตัวอย่างเป็นเพียงสมมติฐาน ไม่ได้รับประกันผลจริง การลงทุนมีความเสี่ยง ผู้ลงทุนอาจสูญเงินต้น</div>
</main>
<script>
var S={sal:0,exp:0,n:50,w:30,step:0,p:0,i:0,c:[]};
try{var raw=localStorage.getItem("fsg");if(raw){var o=JSON.parse(raw);if(o&&typeof o==="object")S=Object.assign(S,o);}}catch(e){}
function save(){try{localStorage.setItem("fsg",JSON.stringify(S));}catch(e){}}
function $(i){return document.getElementById(i)}
function fmt(x){return Math.round(x).toLocaleString("th-TH")}
var STAGES=[
{t:"รู้รายรับรายจ่าย",d:"กรอกเงินเดือนและรายจ่ายจำเป็นด้านบนให้ครบ",m:"ฉันกรอกครบแล้ว",need:function(){return S.sal>0&&S.exp>=0&&S.exp<=S.sal}},
{t:"แบ่งเงินเป็นก้อน",d:"ลากสัดส่วนให้พอดีกับชีวิต อย่างน้อยควรเหลือออมประมาณ 10 เปอร์เซ็นต์",m:"ฉันเลือกสัดส่วนแล้ว",need:function(){return 100-S.n-S.w>=10}},
{t:"สร้างกองทุนฉุกเฉิน",d:"เป้าหมายทั่วไปคือ 3 ถึง 6 เท่าของรายจ่ายต่อเดือน เก็บในที่ถอนง่ายและเงินต้นไม่ผันผวน",m:"ฉันตั้งเป้าเงินสำรองแล้ว"},
{t:"จัดการหนี้ (ถ้ามี)",d:"เรียงหนี้ตามดอกเบี้ยจากสูงไปต่ำ หนี้บัตรเครดิตและสินเชื่อส่วนบุคคลมักแพงที่สุด จ่ายให้ตรงเวลาเสมอ",m:"ฉันเช็กหนี้แล้ว (หรือไม่มีหนี้)"},
{t:"ลงทุนก้อนแรก",d:"อ่านความเสี่ยงให้เข้าใจก่อน แล้วเริ่มทยอยลงเท่า ๆ กันทุกเดือน (DCA) กับกองทุนดัชนีค่าธรรมเนียมต่ำ",m:"เข้าใจความเสี่ยงแล้ว",risk:1}
];
function calc(){
 var s=S.sal,n=S.n,w=S.w,v=Math.max(0,100-n-w);
 $("pn").textContent=n+"%";$("pw").textContent=w+"%";
 $("b1").style.width=n+"%";$("b2").style.width=w+"%";$("b3").style.width=v+"%";
 $("v1").textContent=fmt(s*n/100)+" บาท ("+n+"%)";
 $("v2").textContent=fmt(s*w/100)+" บาท ("+w+"%)";
 $("v3").textContent=fmt(s*v/100)+" บาท ("+v+"%)";
 var sv=s*v/100,f=$("future");
 if(!(sv>0)||!(S.exp>0)){f.innerHTML='<p class="note">กรอกเงินเดือนและรายจ่ายเพื่อดูภาพอนาคต</p>';return}
 var m3=Math.ceil(3*S.exp/sv),m6=Math.ceil(6*S.exp/sv);
 var r=0.05/12,N=120,fv=sv*((Math.pow(1+r,N)-1)/r);
 f.innerHTML='<div class="row"><span>เงินสำรอง 3 เท่าของรายจ่าย</span><span class="big">ใช้เวลาราว '+m3+' เดือน</span></div>'+
 '<div class="row"><span>เงินสำรอง 6 เท่าของรายจ่าย</span><span class="big">ราว '+m6+' เดือน</span></div>'+
 '<div class="row"><span>ถ้าออมก้อนนี้ทุกเดือน 10 ปี</span><span class="big">ราว '+fmt(fv)+' บาท</span></div>'+
 '<p class="note">ตัวอย่างสมมติผลตอบแทน 5% ต่อปี ไม่ใช่ตัวเลขรับประกัน</p>';
}
function stages(){
 var h="";
 STAGES.forEach(function(g,i){
  var cls=i<S.step?"done":i===S.step?"cur":"lock";
  var body='<b>'+g.t+'</b><p>'+g.d+'</p>';
  if(i===S.step){
   if(g.risk){body+='<div class="risk"><span class="tag" style="background:#10b981">ต่ำ</span>เงินฝากและกองทุนตลาดเงิน ความผันผวนน้อย</div><div class="risk"><span class="tag" style="background:#f59e0b">กลาง</span>กองทุนตราสารหนี้และกองทุนผสม</div><div class="risk"><span class="tag" style="background:#ef4444">สูง</span>กองทุนหุ้นและกองทุนดัชนี มูลค่าขึ้นลงแรงและอาจขาดทุนได้ โดยเฉพาะในระยะสั้น</div><p>ใช้เงินเย็นเท่านั้น และควรมีเงินสำรองครบก่อน</p>';}
   var ok=g.need?g.need():true;
   body+=ok?'<button data-i="'+i+'">'+g.m+'</button>':'<p style="color:#d93a3a">ยังไม่ผ่านเงื่อนไขของด่านนี้ ลองตรวจข้อมูลด้านบน</p>';
  }
  h+='<div class="stage '+cls+'"><div class="num">'+(i<S.step?"✓":i+1)+'</div><div>'+body+'</div></div>';
 });
 if(S.step>=STAGES.length)h+='<p class="big">ครบทุกด่านแล้ว เก่งมาก เริ่มทำตามแผนได้เลย</p>';
 $("stages").innerHTML=h;bonus();
}
function tax(n){var b=[[150000,0],[150000,0.05],[200000,0.1],[250000,0.15],[250000,0.2],[1000000,0.25],[3000000,0.3],[Infinity,0.35]],t=0;for(var k=0;k<b.length&&n>0;k++){var x=Math.min(n,b[k][0]);t+=x*b[k][1];n-=x}return t}
function bonus(){
 var inc=S.sal*12,o=$("taxout");
 if(!(inc>0)){o.innerHTML='<p class="note">กรอกเงินเดือนด้านบนเพื่อประมาณภาษี</p>';return}
 var base=Math.min(in
