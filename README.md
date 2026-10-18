<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Повторение лексики — китайский язык</title>
<style>
*{box-sizing:border-box}
body{margin:0;background:#f3f6fb;color:#26334a;font:16px/1.6 Arial,sans-serif}
header{background:#405cc4;color:white;padding:28px 18px;text-align:center}
header h1{margin:0;font-size:30px}
main{max-width:950px;margin:auto;padding:16px}
section{background:white;border-radius:14px;padding:22px;margin:18px 0;box-shadow:0 3px 12px #26334a12}
h2{font-size:22px;margin:0 0 5px}
h3{margin-bottom:8px}
.cn{font-size:19px;font-weight:bold}
.sub{color:#69758a}
button{border:0;border-radius:8px;padding:10px 16px;background:#405cc4;color:white;cursor:pointer;margin:5px 3px}
button:hover{opacity:.85}
select,input,textarea{font:inherit}
select{padding:8px;border:1px solid #ccd4e3;border-radius:8px;max-width:100%;background:white}
.question{padding:12px 0;border-bottom:1px solid #e5e9f1}
.options{display:flex;flex-wrap:wrap;gap:12px;margin-top:8px}
.options label{background:#f3f6fc;padding:7px 10px;border-radius:8px}
.feedback{background:#f1f4fa;padding:12px;border-radius:8px;margin-top:12px}
.good{color:#16804b;font-weight:bold}
.bad{color:#b82d3b;font-weight:bold}
.grid{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}
.cat{border:1px solid #dce3ef;border-radius:10px;padding:12px}
.cat h3{font-size:17px;margin-top:0}
.cat label{display:block;margin:5px 0}
.match{display:grid;grid-template-columns:1fr 1.5fr;gap:12px;align-items:center;padding:9px 0;border-bottom:1px solid #eee}
.wordbank{display:flex;flex-wrap:wrap;gap:8px;margin:12px 0}
.word{background:#eaf0ff;padding:7px 10px;border-radius:7px}
textarea{width:100%;min-height:180px;padding:12px;border:1px solid #ccd4e3;border-radius:10px}
nav{display:flex;flex-wrap:wrap;gap:7px}
nav a{background:white;color:#344b9f;border:1px solid #dce3ef;border-radius:20px;padding:6px 10px;text-decoration:none;font-size:14px}
.builder button{background:#eaf0ff;color:#243d96}
.builder .selected{background:#d9e3ff}
@media(max-width:600px){.grid{grid-template-columns:1fr}.match{grid-template-columns:1fr;gap:4px}section{padding:15px}header h1{font-size:25px}}
</style>
</head>
<body>
<header>
<h1>Повторение лексики</h1>
<p>食物、饮料和饮食习惯 · Еда, напитки и привычки</p>
</header>
<main>
<p>Выполняй задания по порядку. Нажимай «Проверить», чтобы увидеть результат.</p>
<nav>
<a href="#e1">Категории</a><a href="#e2">Лишнее слово</a>
<a href="#e3">Кухни</a><a href="#e4">Пиньинь</a>
<a href="#e5">Перевод</a><a href="#e6">Степень</a>
<a href="#e7">Частота</a><a href="#e8">Пропуски</a>
<a href="#e9">Предложения</a><a href="#e10">Рассказ</a>
</nav>

<section id="e1">
<h2>Упражнение 1. Распредели слова по категориям</h2>
<div class="cn">把词语分类。</div>
<p>Распредели слова по категориям: напитки, готовые блюда и овощи.</p>
<div class="wordbank" id="bank"></div>
<div class="grid" id="cats"></div>
<button onclick="checkCats()">Проверить</button>
<button onclick="resetCats()">Сбросить</button>
<div class="feedback" id="f1"></div>
</section>

<section id="e2">
<h2>Упражнение 2. Что лишнее?</h2>
<div class="cn">哪个词不一样？</div>
<p>Выбери лишнее слово в каждой строке.</p>
<div id="odd"></div>
<button onclick="checkOdd()">Проверить</button>
<button onclick="resetRadios('odd')">Сбросить</button>
<div class="feedback" id="f2"></div>
</section>

<section id="e3">
<h2>Упражнение 3. Распредели блюда</h2>
<div class="cn">把菜分成三类。</div>
<p>中餐 — китайская кухня; 西餐 — западная кухня; 快餐 — фастфуд.</p>
<p class="sub">Для этого упражнения используется один из возможных учебных вариантов классификации.</p>
<div id="cuisine"></div>
<button onclick="checkSelects('cuisine','f3')">Проверить</button>
<button onclick="resetSelects('cuisine','f3')">Сбросить</button>
<div class="feedback" id="f3"></div>
</section>

<section id="e4">
<h2>Упражнение 4. Соедини иероглифы с пиньинем</h2>
<div class="cn">把汉字和拼音连起来。</div>
<div id="pinyin"></div>
<button onclick="checkSelects('pinyin','f4')">Проверить</button>
<button onclick="resetSelects('pinyin','f4')">Сбросить</button>
<div class="feedback" id="f4"></div>
</section>

<section id="e5">
<h2>Упражнение 5. Соедини иероглифы с переводом</h2>
<div class="cn">把汉字和俄语意思连起来。</div>
<div id="translation"></div>
<button onclick="checkSelects('translation','f5')">Проверить</button>
<button onclick="resetSelects('translation','f5')">Сбросить</button>
<div class="feedback" id="f5"></div>
</section>

<section id="e6">
<h2>Упражнение 6. Расположи слова по степени выраженности</h2>
<div class="cn">按照程度排列。</div>
<p>Расположи выражения от менее сильной оценки к наиболее сильной.</p>
<div class="question">
<label>1. Самая низкая степень:
<select id="level1"><option value="">Выбери</option><option>很好吃</option><option>非常好吃</option><option>最好吃</option></select></label>
</div>
<div class="question">
<label>2. Более сильная степень:
<select id="level2"><option value="">Выбери</option><option>很好吃</option><option>非常好吃</option><option>最好吃</option></select></label>
</div>
<div class="question">
<label>3. Высшая оценка:
<select id="level3"><option value="">Выбери</option><option>很好吃</option><option>非常好吃</option><option>最好吃</option></select></label>
</div>
<p>很好吃 — очень вкусно; 非常好吃 — чрезвычайно вкусно; 最好吃 — вкуснее всего.</p>
<button onclick="checkLevels()">Проверить</button>
<div class="feedback" id="f6"></div>
</section>

<section id="e7">
<h2>Упражнение 7. Выбери подходящее слово</h2>
<div class="cn">选择合适的词语。</div>
<p>Вставь 很 ❤️、非常 💕 или 最 ❤️‍🔥.</p>
<div id="degree"></div>
<button onclick="checkSelects('degree','f7')">Проверить</button>
<button onclick="resetSelects('degree','f7')">Сбросить</button>
<div class="feedback" id="f7"></div>
</section>

<section id="e8">
<h2>Упражнение 8. Заполни пропуски</h2>
<div class="cn">完成句子。</div>
<p>Используй 常常 — часто, 有时候 — иногда, 不常 — нечасто, а также 很、非常、最.</p>
<div id="fill"></div>
<button onclick="checkFill()">Проверить</button>
<button onclick="resetSelects('fill','f8')">Сбросить</button>
<div class="feedback" id="f8"></div>
</section>

<section id="e9">
<h2>Упражнение 9. Собери предложение</h2>
<div class="cn">连词成句。</div>
<p>Нажимай на слова в нужном порядке.</p>
<div id="sentenceTask"></div>
<button onclick="checkSentence()">Проверить</button>
<button onclick="nextSentence()">Следующее</button>
<button onclick="resetSentence()">Сбросить</button>
<div class="feedback" id="f9"></div>
</section>

<section id="e10">
<h2>Упражнение 10. Напиши небольшой рассказ</h2>
<div class="cn">我的饮食习惯。</div>
<p>Напиши 8–10 предложений по-китайски.</p>
<h3>План</h3>
<ol>
<li>你喜欢喝什么？</li>
<li>你喜欢吃什么？</li>
<li>你常常吃什么？</li>
<li>你有时候吃什么？</li>
<li>你不常吃什么？</li>
<li>你最喜欢什么菜？</li>
<li>你觉得什么饮料最好喝？</li>
<li>你喜欢中餐、西餐还是快餐？</li>
</ol>
<textarea id="story" placeholder="我的饮食习惯……"></textarea>
<br>
<button onclick="countStory()">Посчитать предложения</button>
<button onclick="document.getElementById('sample').hidden=!document.getElementById('sample').hidden">Показать образец</button>
<div class="feedback" id="f10"></div>
<div id="sample" hidden>
<h3>Образец：我的饮食习惯</h3>
<p class="cn">我喜欢喝茶，也喜欢喝咖啡。我常常喝茶，有时候喝奶茶。我不常喝可可。</p>
<p class="cn">我喜欢吃中餐，也喜欢吃西餐。我常常吃米饭和鸡肉，有时候吃披萨。</p>
<p class="cn">我最喜欢吃饺子。我觉得饺子非常好吃。我也喜欢喝奶茶，我觉得奶茶很好喝。</p>
<p class="cn">我不常吃快餐，因为我更喜欢吃中餐。</p>
</div>
</section>
</main>

<script>
const drinks=['水','咖啡','茶','可可','果汁','牛奶','奶茶','可乐'];
const dishes=['米饭','面条','鸡肉','汤','披萨','薯条','汉堡','包子','饺子','沙拉','牛排','炸鸡'];
const veg=['胡萝卜','西红柿','黄瓜','洋葱','青椒','土豆'];
const all=[...drinks,...dishes,...veg];
const categoryNames=['饮料（напитки）','菜（блюда）','蔬菜（овощи）'];
function options(arr){return '<option value="">— Выбери ответ —</option>'+arr.map(x=>`<option value="${x}">${x}</option>`).join('')}
function shuffle(a){return [...a].sort(()=>Math.random()-.5)}
function row(q,arr,ans){return `<div class="match"><span class="cn">${q}</span><select data-answer="${ans}">${options(arr)}</select></div>`}

document.getElementById('bank').innerHTML=shuffle(all).map(x=>`<span class="word">${x}</span>`).join('');
document.getElementById('cats').innerHTML=[
{title:categoryNames[0],words:drinks,id:'d'},
{title:categoryNames[1],words:dishes,id:'s'},
{title:categoryNames[2],words:veg,id:'v'}
].map(c=>`<div class="cat"><h3>${c.title}</h3>${all.map(w=>`<label><input type="checkbox" data-word="${w}" data-cat="${c.id}"> ${w}</label>`).join('')}</div>`).join('');
document.querySelectorAll('#cats input').forEach(x=>x.addEventListener('change',()=>{
if(x.checked)document.querySelectorAll('#cats input[data-word="'+x.dataset.word+'"]').forEach(y=>{if(y!==x)y.checked=false});
}));
function checkCats(){
let n=0;all.forEach(w=>{let x=document.querySelector('#cats input[data-word="'+w+'"]:checked');let a=drinks.includes(w)?'d':dishes.includes(w)?'s':'v';if(x&&x.dataset.cat===a)n++});
document.getElementById('f1').innerHTML=`Результат: <b>${n} из ${all.length}</b>. ${n===all.length?'Отлично!':'Проверь, чтобы каждое слово было отнесено к правильной категории.'}`;
}
function resetCats(){document.querySelectorAll('#cats input').forEach(x=>x.checked=false);document.getElementById('f1').textContent=''}

const odd=[
[['水','咖啡','牛奶','米饭'],'米饭','米饭 — еда, остальные слова — напитки。'],
[['米饭','面条','饺子','黄瓜'],'黄瓜','黄瓜 — овощ, остальные слова — готовые блюда。'],
[['胡萝卜','土豆','洋葱','奶茶'],'奶茶','奶茶 — напиток, остальные слова — овощи。'],
[['披萨','汉堡','薯条','果汁'],'果汁','果汁 — напиток, остальные слова — блюда / фастфуд。'],
[['茶','可可','咖啡','鸡肉'],'鸡肉','鸡肉 — еда, остальные слова — напитки。'],
[['牛排','炸鸡','包子','青椒'],'青椒','青椒 — овощ, остальные слова — готовые блюда。']
];
document.getElementById('odd').innerHTML=odd.map((q,i)=>`<div class="question"><b>${i+1}.</b> <span class="cn">${q[0].join('、')}</span><div class="options">${q[0].map(w=>`<label><input type="radio" name="odd${i}" value="${w}"> ${w}</label>`).join('')}</div></div>`).join('');
function checkOdd(){let n=0;let out=odd.map((q,i)=>{let x=document.querySelector('input[name="odd'+i+'"]:checked');let ok=x&&x.value===q[1];if(ok)n++;return `<p>${i+1}. ${ok?'<span class="good">Верно</span>':'<span class="bad">Ответ: '+q[1]+'</span>'} — ${q[2]}</p>`}).join('');document.getElementById('f2').innerHTML=`Результат: <b>${n} из 6</b>${out}`}
function resetRadios(id){document.querySelectorAll('#'+id+' input[type=radio]').forEach(x=>x.checked=false);document.getElementById('f2').textContent=''}

const cuisine=[
['米饭','中餐'],['面条','中餐'],['包子','中餐'],['饺子','中餐'],
['披萨','西餐'],['牛排','西餐'],['沙拉','西餐'],['汤','中餐'],
['汉堡','快餐'],['薯条','快餐'],['炸鸡','快餐'],['鸡肉','中餐']
];
document.getElementById('cuisine').innerHTML=cuisine.map(x=>row(x[0],['中餐','西餐','快餐'],x[1])).join('');
const pin=[
['水','shuǐ'],['咖啡','kāfēi'],['茶','chá'],['可可','kěkě'],
['果汁','guǒzhī'],['牛奶','niúnǎi'],['奶茶','nǎichá'],['可乐','kělè'],
['米饭','mǐfàn'],['面条','miàntiáo'],['饺子','jiǎozi'],['胡萝卜','húluóbo']
];
document.getElementById('pinyin').innerHTML=pin.map(x=>row(x[0],shuffle(pin.map(y=>y[1])),x[1])).join('');
const trans=[
['水','вода'],['咖啡','кофе'],['茶','чай'],['可可','какао'],
['果汁','фруктовый сок'],['牛奶','молоко'],['奶茶','чай с молоком'],['可乐','кола'],
['米饭','варёный рис'],['面条','лапша'],['饺子','цзяоцзы / пельмени'],['胡萝卜','морковь']
];
document.getElementById('translation').innerHTML=trans.map(x=>row(x[0],shuffle(trans.map(y=>y[1])),x[1])).join('');

function checkSelects(id,fb){
let els=[...document.querySelectorAll('#'+id+' select')],n=0;
els.forEach(x=>{let ok=x.value===x.dataset.answer;if(ok)n++;x.style.borderColor=ok?'#16804b':x.value?'#b82d3b':'#ccd4e3'});
document.getElementById(fb).innerHTML=`Результат: <b>${n} из ${els.length}</b>. ${n===els.length?'Отличная работа!':'Попробуй исправить ошибки.'}`;
}
function resetSelects(id,fb){document.querySelectorAll('#'+id+' select').forEach(x=>{x.value='';x.style.borderColor='#ccd4e3'});document.getElementById(fb).textContent=''}

function checkLevels(){
const a=['level1','level2','level3'].map(x=>document.getElementById(x).value);
const ok=a[0]==='很好吃'&&a[1]==='非常好吃'&&a[2]==='最好吃';
document.getElementById('f6').innerHTML=ok?'<span class="good">Верно!</span>':'Образец: 很好吃 → 非常好吃 → 最好吃.';
}
const degree=[
['我喜欢喝茶，茶 ______ 好喝。','很','❤️'],
['这家餐厅的饺子 ______ 好吃！我特别喜欢！','非常','💕'],
['这三个菜里面，我觉得鸡肉 ______ 好吃。','最','❤️‍🔥'],
['我觉得咖啡 ______ 好喝，但是我的朋友不喜欢。','很','❤️'],
['我吃过很多披萨，这个披萨 ______ 好吃。','最','❤️‍🔥'],
['这个汤 ______ 好喝，我想再喝一点儿。','非常','💕']
];
document.getElementById('degree').innerHTML=degree.map(x=>`<div class="question"><span>${x[2]}</span> <span class="cn">${x[0]}</span>${row('', ['很','非常','最'],x[1]).replace('<span class="cn"></span>','')}</div>`).join('');

const freq=[
['我每天早上喝咖啡。我 ______ 喝咖啡。','常常'],
['我一个月喝一两次可可。我 ______ 喝可可。','有时候'],
['我不太喜欢喝牛奶。我 ______ 喝牛奶。','不常'],
['星期六和星期天，我 ______ 在家做饭，有时候出去吃饭。','有时候'],
['我很喜欢吃饺子，所以我 ______ 吃饺子。','常常'],
['我工作很忙， ______ 吃午饭的时间不一样。','有时候']
];
const fill=[
['我 ______ 喝茶，每天都喝。',['常常']],
['我 ______ 喝可可，一个月喝一两次。',['有时候']],
['我 ______ 吃快餐，因为我不太喜欢快餐。',['不常']],
['我觉得饺子 ______ 好吃。',['很','非常']],
['在这些饮料里面，我 ______ 喜欢奶茶。',['最']],
['这个汤 ______ 好喝，我很喜欢。',['很','非常']],
['我 ______ 吃披萨，但是我 ______ 吃汉堡。',['常常','不常']],
['我觉得这家餐厅的牛排 ______ 好吃。',['很','非常','最']]
];
document.getElementById('fill').innerHTML=fill.map((x,i)=>`<div class="question"><span class="cn">${x[0]}</span><br>${i===6?row('', ['常常','有时候','不常'],'').replace('data-answer=""','data-answer="常常|有时候"')+row('', ['常常','有时候','不常'],'').replace('data-answer=""','data-answer="不常"'):row('', ['很','非常','最','常常','有时候','不常'],x[1][0])}</div>`).join('');
// Frequency questions are placed separately before the fill exercise.
const freqSection=document.createElement('section');
freqSection.innerHTML='<h2>Дополнительная практика: частота</h2><div class="cn">常常、有时候、不常</div><div id="freqRows"></div><button onclick="checkSelects(\\'freqRows\\',\\'freqFb\\')">Проверить</button><button onclick="resetSelects(\\'freqRows\\',\\'freqFb\\')">Сбросить</button><div class="feedback" id="freqFb"></div>';
document.getElementById('e8').insertAdjacentElement('beforebegin',freqSection);
document.getElementById('freqRows').innerHTML=freq.map(x=>row(x[0],['常常','有时候','不常'],x[1])).join('');

function checkFill(){
let blocks=[...document.querySelectorAll('#fill .question')],score=0;
blocks.forEach((b,i)=>{
let sels=[...b.querySelectorAll('select')],vals=sels.map(s=>s.value);
let ok;
if(i===6)ok=['常常','有时候'].includes(vals[0])&&vals[1]==='不常';
else ok=fill[i][1].includes(vals[0]);
if(ok)score++;
sels.forEach(s=>s.style.borderColor=ok?'#16804b':'#b82d3b');
});
document.getElementById('f8').innerHTML=`Результат: <b>${score} из 8</b>. В предложениях с 很、非常 и 最 возможны разные варианты в зависимости от смысла.`;
}

const sentences=[
{w:['常常','我','喝','茶'],a:'我常常喝茶'},
{w:['最','我','喜欢','饺子'],a:'我最喜欢饺子'},
{w:['很','好吃','这个','汉堡'],a:'这个汉堡很好吃'},
{w:['有时候','我','吃','披萨'],a:'我有时候吃披萨'},
{w:['不常','我','喝','可可'],a:'我不常喝可可'},
{w:['非常','这个','好喝','汤'],a:'这个汤非常好喝'},
{w:['我','常常','吃','米饭','和','鸡肉'],a:'我常常吃米饭和鸡肉'},
{w:['我','最','喜欢','喝','奶茶'],a:'我最喜欢喝奶茶'}
];
let si=0,chosen=[];
function renderSentence(){
chosen=[];
let q=sentences[si];
document.getElementById('sentenceTask').innerHTML=`<p><b>Предложение ${si+1} из ${sentences.length}</b></p><div class="builder">${shuffle(q.w).map((w,i)=>`<button onclick="addWord(this,'${w}')">${w}</button>`).join('')}</div><div class="wordbank" id="chosen"></div>`;
document.getElementById('f9').textContent='';
}
function addWord(btn,w){if(btn.disabled)return;btn.disabled=true;chosen.push({w,btn});drawChosen()}
function drawChosen(){document.getElementById('chosen').innerHTML='';chosen.forEach((x,i)=>{let b=document.createElement('button');b.textContent=x.w;b.style.background='#eaf0ff';b.style.color='#243d96';b.onclick=()=>{x.btn.disabled=false;chosen.splice(i,1);drawChosen()};document.getElementById('chosen').appendChild(b)})}
function checkSentence(){let got=chosen.map(x=>x.w).join('');let ans=sentences[si].a;if(got===ans)document.getElementById('f9').innerHTML='<span class="good">Верно！'+ans+'。</span>';else document.getElementById('f9').innerHTML='Попробуй ещё раз. Образец: <b>'+ans+'。</b>'}
function nextSentence(){si=(si+1)%sentences.length;renderSentence()}
function resetSentence(){renderSentence()}

function countStory(){
let t=document.getElementById('story').value.trim();
let n=t.split(/[。！？!?]+/).filter(x=>x.trim()).length;
document.getElementById('f10').innerHTML=`В тексте примерно <b>${n} предложений</b>. ${n>=8&&n<=10?'<span class="good">Подходит по объёму!</span>':'Напиши 8–10 предложений.'}`;
}
renderSentence();
</script>
</body>
</html>
