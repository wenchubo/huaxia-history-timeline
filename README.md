# huaxia-history-timeline

<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>华夏纪年 · 中国古代历史时间轴</title>
<style>
:root {
  --paper: #f3e5c5;
  --paper-light: #fff5df;
  --ink: #422b1b;
  --brown: #75472a;
  --gold: #b58a45;
  --red: #922f23;
  --border: #c5a775;
}
* { box-sizing: border-box; }
body {
  margin: 0;
  color: var(--ink);
  font-family: "Songti SC", "STSong", "SimSun", serif;
  background:
    radial-gradient(ellipse at 20% 10%, #fff8e5 0, transparent 40%),
    repeating-linear-gradient(0deg, #ead8b4 0, #ead8b4 2px, #e7d2a9 3px, #ead8b4 5px);
}
button, input, select, textarea { font: inherit; }
button { cursor: pointer; }
header {
  text-align: center;
  padding: 38px 16px 24px;
  border-bottom: 4px double var(--gold);
  background: linear-gradient(180deg, #f9edcf, #ead5ac);
}
.seal {
  display: inline-block;
  border: 2px solid var(--red);
  color: var(--red);
  padding: 5px 9px;
  margin-bottom: 10px;
  writing-mode: vertical-rl;
  font-size: 14px;
  letter-spacing: 3px;
}
h1 {
  font-size: clamp(30px, 5vw, 52px);
  letter-spacing: 8px;
  margin: 4px 0 10px;
  text-shadow: 1px 2px 0 #d5bc8c;
}
.subtitle { letter-spacing: 3px; color: #75563a; }
.wrap { width: min(1200px, 94%); margin: 24px auto; }
.panel {
  border: 1px solid var(--border);
  background: rgba(255, 247, 225, .88);
  box-shadow: 0 4px 12px #68431a18;
  padding: 20px;
  margin-bottom: 20px;
  position: relative;
}
.panel::before, .panel::after {
  content: "❧";
  position: absolute;
  color: var(--gold);
  font-size: 22px;
}
.panel::before { left: 8px; top: 4px; }
.panel::after { right: 8px; bottom: 0; }
h2 {
  margin: 0 0 16px;
  font-size: 23px;
  border-bottom: 1px solid var(--border);
  padding: 0 18px 10px;
}
h3 { margin-top: 0; }
.controls {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  align-items: center;
  margin: 12px 0;
}
input, select, textarea {
  border: 1px solid #b89a68;
  background: #fffaf0;
  color: var(--ink);
  padding: 10px;
  border-radius: 3px;
  max-width: 100%;
}
input[type="range"] { width: 100%; accent-color: var(--red); }
button, .file-label {
  border: 1px solid #875b34;
  background: #75472a;
  color: #fff3d8;
  padding: 9px 14px;
  border-radius: 3px;
}
button:hover, .file-label:hover { background: #922f23; }
button.secondary { background: #e8d5ad; color: var(--ink); }
button.active { background: var(--red); }
.small { font-size: 13px; color: #806343; }
.year-display {
  font-size: 32px;
  font-weight: bold;
  text-align: center;
  color: var(--red);
  margin: 10px 0;
}
.timeline {
  position: relative;
  margin: 28px 8px 18px;
  height: 110px;
  border-top: 3px solid var(--brown);
}
.timeline::before {
  content: "";
  position: absolute;
  left: 0; right: 0; top: -9px;
  height: 15px;
  border-top: 1px solid var(--gold);
  border-bottom: 1px solid var(--gold);
  pointer-events: none;
}
.event-dot {
  position: absolute;
  top: -10px;
  transform: translateX(-50%);
  width: 15px; height: 15px;
  padding: 0;
  border-radius: 50%;
  border: 2px solid #fff2d3;
  background: var(--red);
  box-shadow: 0 0 0 1px var(--red);
  z-index: 1;
}
.event-dot:hover, .event-dot.selected {
  transform: translateX(-50%) scale(1.45);
  background: #d6a23d;
}
.event-label {
  position: absolute;
  top: 17px;
  transform: translateX(-50%);
  font-size: 12px;
  writing-mode: vertical-rl;
  max-height: 76px;
  white-space: nowrap;
  overflow: hidden;
  cursor: pointer;
  color: #644328;
}
.event-label:hover { color: var(--red); font-weight: bold; }
.tick-row {
  display: flex;
  justify-content: space-between;
  color: #886d4a;
  font-size: 12px;
}
.grid {
  display: grid;
  grid-template-columns: minmax(0, 1.1fr) minmax(0, .9fr);
  gap: 20px;
}
.event-card {
  background: #fff8e8;
  border: 1px solid #d1b786;
  padding: 18px;
  min-height: 260px;
}
.event-date { color: var(--red); font-size: 14px; }
.event-title { font-size: 27px; margin: 7px 0 12px; }
.tag {
  display: inline-block;
  border: 1px solid #c3a06b;
  color: #80582d;
  padding: 3px 8px;
  margin: 2px;
  font-size: 12px;
}
.detail-block { margin: 12px 0; line-height: 1.8; }
.detail-block strong { color: #7c3927; }
.filter-list { display: flex; flex-wrap: wrap; gap: 7px; }
.filter-list button { padding: 7px 11px; font-size: 14px; }
textarea { width: 100%; min-height: 100px; resize: vertical; }
table { border-collapse: collapse; width: 100%; min-width: 650px; }
th, td {
  border: 1px solid #c8ad7d;
  padding: 9px;
  text-align: left;
  vertical-align: top;
}
th { background: #ead6ad; }
td { background: #fff8e8; }
.table-wrap { overflow-x: auto; }
.records-layout {
  display: grid;
  grid-template-columns: minmax(180px, .28fr) minmax(0, 1fr);
  gap: 16px;
}
.record-list { display: flex; flex-direction: column; gap: 6px; }
.record-list button { text-align: left; }
footer {
  text-align: center;
  padding: 24px 12px 35px;
  color: #806343;
  font-size: 13px;
}
.empty { color: #997e5a; padding: 18px 0; }
@media (max-width: 760px) {
  .grid, .records-layout { grid-template-columns: 1fr; }
  .panel { padding: 15px; }
  h1 { letter-spacing: 3px; }
  .timeline { margin-left: 4px; margin-right: 4px; }
}
</style>
</head>
<body>
<header>
  <div class="seal">华夏纪年</div>
  <h1>中国古代历史时间轴</h1>
  <div class="subtitle">观千年兴替 · 览华夏文明</div>
</header>

<main class="wrap">
  <section class="panel">
    <h2>一、纪年检索</h2>
    <div class="controls">
      <label for="dynastyFilter">朝代：</label>
      <select id="dynastyFilter">
        <option value="all">全部朝代</option>
      </select>
      <label for="topicFilter">主题：</label>
      <select id="topicFilter">
        <option value="all">全部主题</option>
        <option>政治</option><option>经济</option><option>文化</option>
        <option>民族关系</option><option>对外交流</option><option>科技</option>
        <option>战争与统一</option>
      </select>
      <input id="searchInput" placeholder="搜索事件、人物或关键词…" aria-label="搜索历史事件">
      <button id="resetBtn" class="secondary">重置筛选</button>
    </div>
    <div class="year-display" id="yearDisplay">公元前 2070 年</div>
    <label for="yearSlider">拖动滑块，浏览不同年代</label>
    <input id="yearSlider" type="range" min="-2070" max="1912" value="-2070" step="1">
    <div class="tick-row">
      <span>前2070年</span><span>前221年</span><span>公元元年</span><span>618年</span><span>1368年</span><span>1912年</span>
    </div>
    <div class="timeline" id="timeline"></div>
    <p class="small">红点代表历史事件。点击时间轴上的圆点或事件文字，可查看详细介绍。</p>
  </section>

  <section class="panel">
    <h2>二、朝代索引</h2>
    <div class="filter-list" id="dynastyButtons"></div>
  </section>

  <div class="grid">
    <section class="panel">
      <h2>三、历史事件</h2>
      <div id="eventList"></div>
    </section>
    <section class="panel">
      <h2>四、事件详录</h2>
      <article class="event-card" id="eventDetail">
        <div class="empty">请选择时间轴上的历史事件。</div>
      </article>
    </section>
  </div>

  <section class="panel">
    <h2>五、读史札记</h2>
    <p class="small">为当前选中的历史事件写下自己的理解。内容保存在当前浏览器中。</p>
    <div id="noteEventName">尚未选择事件</div>
    <textarea id="eventNote" placeholder="记录事件背景、历史影响、易错知识点或自己的思考……"></textarea>
    <div class="controls">
      <button id="saveNoteBtn">保存札记</button>
      <button id="clearNoteBtn" class="secondary">清空当前札记</button>
      <span class="small" id="noteStatus"></span>
    </div>
  </section>

  <section class="panel">
    <h2>六、朝代记录簿</h2>
    <p class="small">选择朝代，整理这一时期的政治、经济、文化与重要事件。记录会保存在当前浏览器中。</p>
    <div class="records-layout">
      <div class="record-list" id="recordDynasties"></div>
      <div>
        <h3 id="recordHeading">请选择朝代</h3>
        <div class="controls">
          <input id="recordDate" placeholder="时间，如：公元前221年">
          <input id="recordTitle" placeholder="事件名称">
        </div>
        <div class="controls">
          <select id="recordTopic">
            <option>政治</option><option>经济</option><option>文化</option>
            <option>民族关系</option><option>对外交流</option><option>科技</option>
            <option>战争与统一</option>
          </select>
          <input id="recordPeople" placeholder="相关人物（选填）">
        </div>
        <textarea id="recordContent" placeholder="事件经过、主要内容、历史影响……"></textarea>
        <div class="controls">
          <button id="addRecordBtn">添加记录</button>
          <button id="exportRecordsBtn" class="secondary">导出本朝记录 CSV</button>
          <button id="exportAllBtn" class="secondary">导出全部记录 CSV</button>
        </div>
        <div class="table-wrap">
          <table>
            <thead><tr><th>时间</th><th>事件</th><th>主题</th><th>相关人物</th><th>内容</th><th>操作</th></tr></thead>
            <tbody id="recordTableBody"></tbody>
          </table>
        </div>
      </div>
    </div>
  </section>

  <section class="panel">
    <h2>七、历史事件数据导出</h2>
    <p>可以将网站内置的历史事件导出为 CSV 文件，用于复习、整理或在表格软件中继续编辑。</p>
    <div class="controls">
      <button id="exportEventsBtn">导出全部历史事件 CSV</button>
      <button id="exportNotesBtn" class="secondary">导出全部札记 CSV</button>
    </div>
    <p class="small">说明：本网站为学习整理工具，事件列表是基础示例，不能替代完整教材。具体年代、史实和教材表述请结合人教版教材核对。</p>
  </section>
</main>

<footer>以史为鉴，知古鉴今 · 华夏纪年</footer>

<script>
const events = [
{id:1,year:-2070,date:"约公元前2070年",dynasty:"夏",title:"夏朝建立",topic:"政治",people:"禹",summary:"传统史学通常将夏朝建立视为中国早期国家发展的重要标志。",background:"传说禹因治水有功而受到拥戴，部落联盟的权力结构逐步变化。",impact:"夏朝的建立反映了早期国家形态的发展。夏朝的具体历史仍有需要继续研究的问题。",keywords:["早期国家","王位世袭"]},
{id:2,year:-1600,date:"约公元前1600年",dynasty:"商",title:"商朝建立",topic:"政治",people:"汤",summary:"商汤灭夏，建立商朝。",background:"夏末统治衰落，商部族势力逐渐发展。",impact:"商朝发展了青铜文明，甲骨文为研究当时社会提供了重要材料。",keywords:["商汤","甲骨文","青铜器"]},
{id:3,year:-1300,date:"约公元前1300年",dynasty:"商",title:"盘庚迁殷",topic:"政治",people:"盘庚",summary:"商王盘庚迁都于殷，商朝统治逐渐稳定。",background:"商朝前期曾多次迁都，统治秩序面临调整。",impact:"殷墟遗址及出土文物为研究商朝历史提供了重要依据。",keywords:["殷墟","商朝"]},
{id:4,year:-1046,date:"公元前1046年",dynasty:"西周",title:"牧野之战与西周建立",topic:"战争与统一",people:"周武王",summary:"周武王率军在牧野击败商军，商朝灭亡，西周建立。",background:"商纣王统治末期，社会矛盾加剧，周部族势力增强。",impact:"周朝建立后实行分封制等制度，以巩固统治。",keywords:["牧野之战","周武王","分封制"]},
{id:5,year:-841,date:"公元前841年",dynasty:"西周",title:"国人暴动与共和行政",topic:"政治",people:"周厉王",summary:"周厉王时期发生国人暴动，此后进入共和行政时期。",background:"周厉王统治时期社会矛盾尖锐。",impact:"这一事件反映了西周统治危机，是中国古代纪年史上的重要节点。",keywords:["国人暴动","共和行政"]},
{id:6,year:-770,date:"公元前770年",dynasty:"东周",title:"平王东迁",topic:"政治",people:"周平王",summary:"周平王迁都洛邑，东周开始。",background:"西周末年王室衰微，犬戎入侵。",impact:"周王室权威进一步下降，诸侯势力逐渐增强，春秋时期到来。",keywords:["东周","春秋"]},
{id:7,year:-551,date:"传统说法：公元前551年",dynasty:"春秋",title:"孔子诞生",topic:"文化",people:"孔子",summary:"孔子是儒家学派的代表人物之一。",background:"春秋时期社会秩序发生变化，思想文化日益活跃。",impact:"孔子的思想对中国传统文化、教育和伦理观念产生了深远影响。",keywords:["儒家","仁","教育"]},
{id:8,year:-475,date:"约公元前475年",dynasty:"战国",title:"战国时期开始",topic:"政治",people:"各诸侯国",summary:"战国时期各诸侯国竞争加剧，兼并战争频繁。",background:"春秋以来诸侯势力发展，周王室影响力不断减弱。",impact:"各国变法推动社会转型，思想文化领域出现百家争鸣局面。",keywords:["战国七雄","变法","百家争鸣"]},
{id:9,year:-356,date:"公元前356年起",dynasty:"战国",title:"商鞅变法",topic:"政治",people:"秦孝公、商鞅",summary:"秦国推行变法，改革政治、经济和军事制度。",background:"秦国希望增强国力，在诸侯竞争中取得优势。",impact:"变法增强了秦国实力，为后来统一六国奠定了基础。",keywords:["县制","奖励军功","变法"]},
{id:10,year:-256,date:"公元前256年",dynasty:"战国",title:"都江堰修建",topic:"经济",people:"李冰",summary:"秦国蜀郡守李冰主持修建都江堰水利工程。",background:"成都平原需要治理水患并发展农业灌溉。",impact:"工程发挥防洪、灌溉等作用，促进成都平原农业发展。",keywords:["水利工程","农业","蜀郡"]},
{id:11,year:-221,date:"公元前221年",dynasty:"秦",title:"秦统一六国",topic:"战争与统一",people:"秦始皇",summary:"秦王嬴政完成统一，建立秦朝。",background:"商鞅变法后秦国实力增强，兼并战争持续推进。",impact:"统一结束长期分裂局面，建立起中央集权国家。",keywords:["统一","秦始皇","中央集权"]},
{id:12,year:-221,date:"公元前221年后",dynasty:"秦",title:"秦朝巩固统一的措施",topic:"政治",people:"秦始皇、李斯",summary:"秦朝推行郡县制，并统一文字、货币、度量衡等。",background:"统一后各地制度存在差异，需要建立共同的治理体系。",impact:"加强中央对地方的控制，推动经济文化交流。",keywords:["郡县制","小篆","圆形方孔钱"]},
{id:13,year:-209,date:"公元前209年",dynasty:"秦",title:"陈胜、吴广起义",topic:"战争与统一",people:"陈胜、吴广",summary:"秦末农民起义爆发，秦朝统治受到重大冲击。",background:"秦朝徭役繁重，法律严苛，社会矛盾突出。",impact:"起义动摇了秦朝统治，为秦朝灭亡揭开序幕。",keywords:["大泽乡","秦末起义"]},
{id:14,year:-202,date:"公元前202年",dynasty:"西汉",title:"西汉建立",topic:"政治",people:"刘邦",summary:"刘邦击败项羽后建立汉朝，定都长安。",background:"秦朝灭亡后，楚汉之间展开长期战争。",impact:"汉朝逐步恢复社会经济，形成新的政治秩序。",keywords:["刘邦","楚汉战争","长安"]},
{id:15,year:-154,date:"公元前154年",dynasty:"西汉",title:"七国之乱",topic:"政治",people:"汉景帝",summary:"部分诸侯王起兵反叛，汉朝中央最终平定叛乱。",background:"汉初分封诸侯王，部分诸侯国势力强大。",impact:"中央加强对诸侯王的控制，推动中央集权进一步发展。",keywords:["诸侯王","中央集权"]},
{id:16,year:-138,date:"公元前138年",dynasty:"西汉",title:"张骞第一次出使西域",topic:"对外交流",people:"张骞",summary:"张骞奉命出使西域，尝试联络大月氏等力量。",background:"汉武帝希望联合西域力量应对匈奴。",impact:"加深了中原王朝对西域的了解，为丝绸之路的发展创造条件。",keywords:["张骞","西域","丝绸之路"]},
{id:17,year:-119,date:"公元前119年",dynasty:"西汉",title:"漠北之战",topic:"战争与统一",people:"卫青、霍去病",summary:"汉军在漠北取得重要军事胜利。",background:"汉朝与匈奴长期争夺北方边境与交通通道。",impact:"改变了汉匈力量对比，推动汉朝经营北方边疆。",keywords:["卫青","霍去病","匈奴"]},
{id:18,year:-60,date:"公元前60年",dynasty:"西汉",title:"西域都护设立",topic:"民族关系",people:"西汉中央政府",summary:"西汉设立西域都护，管理西域相关事务。",background:"汉朝与西域联系加强，需要建立行政管理机构。",impact:"标志着西汉对西域的管理进一步加强。",keywords:["西域都护","边疆治理"]},
{id:19,year:25,date:"公元25年",dynasty:"东汉",title:"东汉建立",topic:"政治",people:"刘秀",summary:"刘秀建立东汉，定都洛阳。",background:"王莽新朝末年社会动荡，各地起义不断。",impact:"汉朝政权得以重建，社会秩序逐渐恢复。",keywords:["光武帝","洛阳"]},
{id:20,year:105,date:"公元105年",dynasty:"东汉",title:"蔡伦改进造纸工艺",topic:"科技",people:"蔡伦",summary:"蔡伦总结并改进造纸工艺，促进纸张应用。",background:"社会对书写材料的需求不断增长。",impact:"造纸术的发展促进知识传播，并逐渐影响世界文明。",keywords:["造纸术","科技传播"]},
{id:21,year:184,date:"公元184年",dynasty:"东汉",title:"黄巾起义",topic:"战争与统一",people:"张角",summary:"黄巾起义爆发，东汉统治受到沉重打击。",background:"东汉后期政治腐败，土地兼并与社会矛盾突出。",impact:"东汉中央权威进一步削弱，地方军阀势力增长。",keywords:["黄巾军","东汉衰落"]},
{id:22,year:200,date:"公元200年",dynasty:"三国",title:"官渡之战",topic:"战争与统一",people:"曹操、袁绍",summary:"曹操在官渡击败袁绍，为统一北方奠定基础。",background:"东汉末年群雄并起，北方势力竞争激烈。",impact:"北方政治军事格局发生重要变化。",keywords:["曹操","袁绍"]},
{id:23,year:208,date:"公元208年",dynasty:"三国",title:"赤壁之战",topic:"战争与统一",people:"曹操、孙权、刘备",summary:"孙刘联军在赤壁击败曹操军队。",background:"曹操南下，希望进一步统一南方。",impact:"形成三国鼎立局面的重要基础。",keywords:["赤壁","孙刘联军","三国鼎立"]},
{id:24,year:220,date:"公元220年",dynasty:"三国",title:"魏国建立",topic:"政治",people:"曹丕",summary:"曹丕称帝，建立魏国，东汉结束。",background:"东汉末年中央政权名存实亡，曹操掌握北方大权。",impact:"此后蜀汉、孙吴相继建立，三国鼎立局面形成。",keywords:["曹丕","三国"]},
{id:25,year:266,date:"公元266年",dynasty:"西晋",title:"西晋建立",topic:"政治",people:"司马炎",summary:"司马炎建立西晋。",background:"魏国后期司马氏掌握政权。",impact:"西晋后来完成短暂统一，但内部矛盾仍然突出。",keywords:["司马炎","西晋"]},
{id:26,year:280,date:"公元280年",dynasty:"西晋",title:"西晋统一全国",topic:"战争与统一",people:"司马炎",summary:"西晋灭吴，结束三国分裂局面。",background:"三国时期长期战争后，魏晋力量对比发生变化。",impact:"全国再次统一，但统治持续时间不长。",keywords:["灭吴","短暂统一"]},
{id:27,year:383,date:"公元383年",dynasty:"东晋",title:"淝水之战",topic:"战争与统一",people:"谢安、苻坚",summary:"东晋军队击败前秦军队。",background:"前秦试图南下统一南北。",impact:"前秦统治迅速瓦解，南北对峙格局延续。",keywords:["东晋","前秦","以少胜多"]},
{id:28,year:420,date:"公元420年",dynasty:"南北朝",title:"南朝宋建立",topic:"政治",people:"刘裕",summary:"刘裕建立刘宋，南朝开始。",background:"东晋后期政局变化，军事将领势力上升。",impact:"此后南方经历宋、齐、梁、陈等政权更替。",keywords:["南朝","政权更替"]},
{id:29,year:485,date:"公元485年",dynasty:"北魏",title:"北魏推行均田制",topic:"经济",people:"北魏孝文帝时期",summary:"北魏推行均田制，调整土地分配与赋役管理。",background:"北方长期战乱后，社会经济需要恢复。",impact:"有助于恢复农业生产，并影响后世土地与赋役制度。",keywords:["均田制","农业恢复"]},
{id:30,year:494,date:"公元494年",dynasty:"北魏",title:"北魏孝文帝迁都洛阳",topic:"民族关系",people:"北魏孝文帝",summary:"北魏迁都洛阳，并进一步推行汉化改革。",background:"北魏希望加强对中原地区的治理。",impact:"促进民族交融与北方社会文化发展。",keywords:["迁都洛阳","汉化改革","民族交融"]},
{id:31,year:581,date:"公元581年",dynasty:"隋",title:"隋朝建立",topic:"政治",people:"杨坚",summary:"杨坚建立隋朝，结束北周统治。",background:"北方政权更替后，统一条件逐渐成熟。",impact:"隋朝随后完成全国统一，推动制度建设。",keywords:["隋文帝","隋朝"]},
{id:32,year:589,date:"公元589年",dynasty:"隋",title:"隋统一全国",topic:"战争与统一",people:"隋文帝",summary:"隋军灭陈，结束长期分裂局面。",background:"南北朝以来分裂局面延续数百年。",impact:"全国统一促进南北经济文化交流。",keywords:["灭陈","南北统一"]},
{id:33,year:605,date:"公元605年起",dynasty:"隋",title:"大运河开通与发展",topic:"经济",people:"隋炀帝",summary:"隋朝大规模开凿和疏通运河，形成重要水运网络。",background:"统一国家需要加强南北交通和物资运输。",impact:"加强南北经济联系，但工程也带来沉重的社会负担。",keywords:["大运河","南北交通"]},
{id:34,year:618,date:"公元618年",dynasty:"唐",title:"唐朝建立",topic:"政治",people:"李渊",summary:"李渊建立唐朝，定都长安。",background:"隋末社会动荡，各地起义和割据势力兴起。",impact:"唐朝逐渐发展成为当时世界上具有重要影响力的政权。",keywords:["李渊","长安"]},
{id:35,year:627,date:"公元627年起",dynasty:"唐",title:"贞观之治",topic:"政治",people:"唐太宗",summary:"唐太宗统治时期重视纳谏、用人和制度建设。",background:"唐初需要恢复经济、稳定统治。",impact:"政治较为清明，社会经济得到发展。",keywords:["唐太宗","纳谏","治理"]},
{id:36,year:641,date:"公元641年",dynasty:"唐",title:"文成公主入藏",topic:"民族关系",people:"文成公主、松赞干布",summary:"文成公主入藏，唐与吐蕃交往进一步发展。",background:"唐朝与吐蕃建立了多方面的联系。",impact:"促进双方经济文化交流，是唐蕃关系的重要事件。",keywords:["吐蕃","唐蕃交往"]},
{id:37,year:690,date:"公元690年",dynasty:"唐",title:"武则天称帝",topic:"政治",people:"武则天",summary:"武则天建立武周政权，成为中国历史上唯一的正统女皇帝。",background:"唐高宗后期武则天逐步掌握朝廷大权。",impact:"统治期间继续发展科举，并采取措施治理国家。",keywords:["武周","科举"]},
{id:38,year:755,date:"公元755年",dynasty:"唐",title:"安史之乱爆发",topic:"战争与统一",people:"安禄山、史思明",summary:"安史之乱爆发，唐朝社会遭受严重冲击。",background:"唐朝后期藩镇势力发展，中央与地方矛盾加剧。",impact:"唐朝由盛转衰，藩镇割据问题进一步突出。",keywords:["安史之乱","唐朝衰落"]},
{id:39,year:875,date:"公元875年起",dynasty:"唐",title:"黄巢起义",topic:"战争与统一",people:"黄巢",summary:"黄巢领导的起义沉重打击唐朝统治。",background:"唐末政治腐败，赋役沉重，社会矛盾激化。",impact:"唐朝统治进一步瓦解，地方割据加剧。",keywords:["黄巢","唐末"]},
{id:40,year:907,date:"公元907年",dynasty:"五代十国",title:"唐朝灭亡",topic:"政治",people:"朱温",summary:"唐朝灭亡，中国进入五代十国时期。",background:"唐末藩镇势力强大，中央政权衰弱。",impact:"北方政权频繁更迭，南方多个政权并立。",keywords:["五代十国","藩镇"]},
{id:41,year:960,date:"公元960年",dynasty:"北宋",title:"北宋建立",topic:"政治",people:"赵匡胤",summary:"赵匡胤建立宋朝，定都东京开封府。",background:"五代时期政权更迭频繁。",impact:"宋朝加强中央集权，推动经济与文化发展。",keywords:["陈桥兵变","宋太祖"]},
{id:42,year:1005,date:"公元1005年",dynasty:"北宋",title:"澶渊之盟",topic:"民族关系",people:"宋真宗、辽",summary:"宋辽议和，双方形成较长时期的相对稳定关系。",background:"宋辽之间长期发生战争。",impact:"宋辽边境贸易与交往有所发展。",keywords:["宋辽关系","议和"]},
{id:43,year:1044,date:"公元1044年",dynasty:"北宋",title:"宋夏和议",topic:"民族关系",people:"北宋、西夏",summary:"宋与西夏达成和议。",background:"宋夏之间战争持续，双方均希望缓和冲突。",impact:"边境关系趋于缓和，双方继续保持交往。",keywords:["西夏","宋夏关系"]},
{id:44,year:1069,date:"公元1069年起",dynasty:"北宋",title:"王安石变法",topic:"政治",people:"王安石、宋神宗",summary:"北宋推行一系列改革措施，希望富国强兵。",background:"北宋面临财政压力、军事压力与行政问题。",impact:"变法引发广泛争论，反映了宋代治理的复杂性。",keywords:["青苗法","变法争论"]},
{id:45,year:1115,date:"公元1115年",dynasty:"金",title:"金朝建立",topic:"政治",people:"完颜阿骨打",summary:"女真族建立金朝。",background:"女真各部逐渐发展，反抗辽朝统治。",impact:"辽、宋、金之间的政治军事格局发生变化。",keywords:["女真","完颜阿骨打"]},
{id:46,year:1127,date:"公元1127年",dynasty:"南宋",title:"南宋建立",topic:"政治",people:"赵构",summary:"北宋灭亡后，赵构建立南宋，定都临安。",background:"金军南下，北宋都城陷落。",impact:"南宋与金长期对峙，南方经济文化继续发展。",keywords:["靖康之变","临安"]},
{id:47,year:1206,date:"公元1206年",dynasty:"蒙古",title:"蒙古政权建立",topic:"政治",people:"铁木真",summary:"铁木真被尊为成吉思汗，蒙古各部逐步统一。",background:"蒙古草原各部长期存在竞争与冲突。",impact:"蒙古势力迅速发展，改变欧亚大陆政治格局。",keywords:["成吉思汗","蒙古统一"]},
{id:48,year:1271,date:"公元1271年",dynasty:"元",title:"元朝国号确立",topic:"政治",people:"忽必烈",summary:"忽必烈定国号为大元。",background:"蒙古政权持续扩张，并推进中原治理。",impact:"元朝进一步推进统一，实行行省制度等治理措施。",keywords:["忽必烈","行省制度"]},
{id:49,year:1279,date:"公元1279年",dynasty:"元",title:"元朝完成统一",topic:"战争与统一",people:"元军、南宋",summary:"元军攻灭南宋残余力量，全国实现统一。",background:"蒙古势力南下，南宋政权持续衰弱。",impact:"元朝建立起疆域广阔的统一政权，民族交往进一步发展。",keywords:["统一","元朝"]},
{id:50,year:1405,date:"公元1405年起",dynasty:"明",title:"郑和下西洋",topic:"对外交流",people:"郑和",summary:"郑和率船队多次远航，访问亚非多个地区。",background:"明朝希望加强海外联系并展示国力。",impact:"促进中外交流，展现当时中国航海技术与组织能力。",keywords:["郑和","海上交通"]},
{id:51,year:1421,date:"公元1421年",dynasty:"明",title:"明朝迁都北京",topic:"政治",people:"明成祖",summary:"明朝正式迁都北京。",background:"明成祖时期北方战略地位受到重视。",impact:"北京成为此后多个王朝的重要政治中心。",keywords:["北京","明成祖"]},
{id:52,year:1368,date:"公元1368年",dynasty:"明",title:"明朝建立",topic:"政治",people:"朱元璋",summary:"朱元璋建立明朝，定都应天府。",background:"元末社会动荡，各地起义不断。",impact:"明朝重建汉地王朝统治，并逐步整顿国家制度。",keywords:["朱元璋","明朝"]},
{id:53,year:1557,date:"16世纪中叶",dynasty:"明",title:"澳门贸易与中外交流",topic:"对外交流",people:"明朝地方官员、葡萄牙商人",summary:"澳门逐渐发展为中外贸易与交流的重要地点。",background:"明代沿海贸易与海外交流不断变化。",impact:"澳门成为近代早期中外经济文化交流的重要窗口。",keywords:["澳门","海上贸易"]},
{id:54,year:1616,date:"公元1616年",dynasty:"后金",title:"后金建立",topic:"政治",people:"努尔哈赤",summary:"努尔哈赤建立后金政权。",background:"女真各部在努尔哈赤领导下逐渐统一。",impact:"后金不断发展，后来改国号为清并入主中原。",keywords:["努尔哈赤","后金"]},
{id:55,year:1636,date:"公元1636年",dynasty:"清",title:"清朝国号确立",topic:"政治",people:"皇太极",summary:"皇太极改国号为清。",background:"后金政权持续发展，并调整国家制度。",impact:"清朝建立前的重要政治步骤，之后继续向中原发展。",keywords:["皇太极","清"]},
{id:56,year:1644,date:"公元1644年",dynasty:"清",title:"清军入关",topic:"战争与统一",people:"清军、李自成",summary:"明朝灭亡后，清军进入山海关并逐步控制北京。",background:"明末社会矛盾尖锐，农民起义与边疆军事压力交织。",impact:"中国政权格局发生重大变化，清朝开始建立全国统治。",keywords:["明朝灭亡","清朝入关"]},
{id:57,year:1684,date:"公元1684年",dynasty:"清",title:"清朝设置台湾府",topic:"民族关系",people:"清朝中央政府",summary:"清朝设置台湾府，隶属福建省。",background:"清朝统一台湾后，需要加强行政管理。",impact:"加强了中央政府对台湾的行政治理。",keywords:["台湾府","边疆治理"]},
{id:58,year:1689,date:"公元1689年",dynasty:"清",title:"中俄《尼布楚条约》签订",topic:"对外交流",people:"清朝、俄国",summary:"清俄双方签订条约，处理东北边界问题。",background:"清俄在边境地区发生冲突，需要通过谈判解决。",impact:"条约对两国东段边界作出规定，是清初边疆外交的重要事件。",keywords:["尼布楚条约","边界"]},
{id:59,year:1727,date:"公元1727年",dynasty:"清",title:"清朝设驻藏大臣",topic:"民族关系",people:"清朝中央政府",summary:"清朝设置驻藏大臣，参与西藏地方事务管理。",background:"清朝逐步完善对边疆地区的治理制度。",impact:"清朝加强了对西藏地方事务的管理。",keywords:["驻藏大臣","边疆治理"]},
{id:60,year:1793,date:"公元1793年",dynasty:"清",title:"《钦定藏内善后章程》相关制度",topic:"民族关系",people:"清朝中央政府",summary:"清朝通过相关章程调整西藏地方治理制度。",background:"清朝希望进一步规范西藏地方行政事务。",impact:"相关制度体现了清朝对边疆治理的制度化尝试。",keywords:["西藏","边疆制度"]},
{id:61,year:1840,date:"公元1840年",dynasty:"清",title:"鸦片战争爆发",topic:"战争与统一",people:"清朝、英国",summary:"英国发动鸦片战争，中国近代史由此开启。",background:"中英贸易矛盾、鸦片走私及清政府禁烟等因素交织。",impact:"战争改变中国社会发展进程，传统社会面临严重冲击。",keywords:["鸦片战争","近代史开端"]},
{id:62,year:1842,date:"公元1842年",dynasty:"清",title:"《南京条约》签订",topic:"对外交流",people:"清朝、英国",summary:"清政府与英国签订《南京条约》。",background:"清朝在鸦片战争中战败。",impact:"中国主权受到损害，开始逐步沦为半殖民地半封建社会。",keywords:["南京条约","五口通商"]},
{id:63,year:1861,date:"公元1861年起",dynasty:"清",title:"洋务运动开展",topic:"经济",people:"曾国藩、李鸿章、左宗棠等",summary:"清朝部分官员开展以学习西方技术为主要内容的自强运动。",background:"清政府在内忧外患中寻求强化军事与工业能力。",impact:"推动近代军事工业、民用工业及新式教育发展，但未能从根本上改变清朝危机。",keywords:["洋务运动","近代工业"]},
{id:64,year:1894,date:"公元1894年",dynasty:"清",title:"甲午中日战争爆发",topic:"战争与统一",people:"清朝、日本",summary:"日本发动战争，清军战败。",background:"日本加快对外扩张，朝鲜问题成为冲突导火索。",impact:"战争失败暴露清朝制度与军事问题，推动中国社会进一步变化。",keywords:["甲午战争","民族危机"]},
{id:65,year:1898,date:"公元1898年",dynasty:"清",title:"戊戌变法",topic:"政治",people:"康有为、梁启超、光绪帝",summary:"维新派推动变法，试图改革政治和教育制度。",background:"甲午战争后民族危机加深，改革呼声高涨。",impact:"变法很快失败，但推动了思想传播与政治改革讨论。",keywords:["维新变法","改革"]},
{id:66,year:1900,date:"公元1900年",dynasty:"清",title:"八国联军侵华",topic:"战争与统一",people:"清朝、八国联军",summary:"八国联军侵入中国，清政府面临严重危机。",background:"列强侵略加剧，义和团运动与列强矛盾激化。",impact:"中国主权进一步受损，清政府被迫承担沉重赔款。",keywords:["八国联军","列强侵略"]},
{id:67,year:1901,date:"公元1901年",dynasty:"清",title:"《辛丑条约》签订",topic:"对外交流",people:"清政府、列强",summary:"清政府与列强签订《辛丑条约》。",background:"八国联军侵华后清政府战败。",impact:"中国半殖民地半封建社会程度进一步加深。",keywords:["辛丑条约","赔款"]},
{id:68,year:1911,date:"公元1911年",dynasty:"清",title:"辛亥革命爆发",topic:"政治",people:"革命党人",summary:"武昌起义爆发，各省响应，清朝统治迅速瓦解。",background:"清末改革未能化解政治危机，革命力量不断发展。",impact:"推动清朝灭亡和中国政治制度的重大转变。",keywords:["武昌起义","辛亥革命"]},
{id:69,year:1912,date:"公元1912年",dynasty:"清",title:"清帝退位",topic:"政治",people:"宣统帝、孙中山等",summary:"清帝退位，清朝统治结束。",background:"辛亥革命后，各方推动政权交接。",impact:"中国两千多年君主专制制度结束，中华民国建立。",keywords:["清朝灭亡","君主专制结束"]}
];

const dynasties = ["夏","商","西周","东周","春秋","战国","秦","西汉","东汉","三国","西晋","东晋","南北朝","北魏","隋","唐","五代十国","北宋","南宋","金","蒙古","元","明","后金","清"];
const $ = id => document.getElementById(id);
let selectedEvent = null;
let selectedRecordDynasty = "夏";
let records = load("huaxia_records", {});
let notes = load("huaxia_notes", {});

function load(key, fallback) {
  try { return JSON.parse(localStorage.getItem(key)) || fallback; }
  catch(e) { return fallback; }
}
function save(key, value) {
  try { localStorage.setItem(key, JSON.stringify(value)); return true; }
  catch(e) { return false; }
}
function yearText(y) {
  if (y < 0) return "公元前 " + Math.abs(y) + " 年";
  if (y === 0) return "公元前1年与公元1年之间";
  return "公元 " + y + " 年";
}
function filteredEvents() {
  const dynasty = $("dynastyFilter").value;
  const topic = $("topicFilter").value;
  const q = $("searchInput").value.trim().toLowerCase();
  return events.filter(e =>
    (dynasty === "all" || e.dynasty === dynasty) &&
    (topic === "all" || e.topic === topic) &&
    (!q || [e.title,e.dynasty,e.people,e.summary,e.topic,...e.keywords].join(" ").toLowerCase().includes(q))
  );
}
function initFilters() {
  dynasties.forEach(d => {
    const option = document.createElement("option");
    option.value = d; option.textContent = d + "朝";
    $("dynastyFilter").appendChild(option);
  });
  $("dynastyButtons").innerHTML = "";
  ["全部朝代", ...dynasties].forEach(d => {
    const b = document.createElement("button");
    b.textContent = d;
    b.className = "secondary";
    b.onclick = () => {
      $("dynastyFilter").value = d === "全部朝代" ? "all" : d;
      renderAll();
    };
    $("dynastyButtons").appendChild(b);
  });
  $("recordDynasties").innerHTML = "";
  dynasties.forEach(d => {
    const b = document.createElement("button");
    b.textContent = d + "朝";
    b.className = "secondary";
    b.onclick = () => { selectedRecordDynasty = d; renderRecords(); };
    $("recordDynasties").appendChild(b);
  });
}
function renderTimeline() {
  const visible = filteredEvents();
  const area = $("timeline");
  area.innerHTML = "";
  visible.forEach(e => {
    const pct = ((e.year + 2070) / (1912 + 2070)) * 100;
    const dot = document.createElement("button");
    dot.className = "event-dot" + (selectedEvent && selectedEvent.id === e.id ? " selected" : "");
    dot.style.left = pct + "%";
    dot.title = e.date + " · " + e.title;
    dot.setAttribute("aria-label", e.title);
    dot.onclick = () => selectEvent(e);
    area.appendChild(dot);
    const label = document.createElement("span");
    label.className = "event-label";
    label.style.left = pct + "%";
    label.textContent = e.title;
    label.title = e.title;
    label.onclick = () => selectEvent(e);
    area.appendChild(label);
  });
  if (!visible.length) area.innerHTML = '<div class="empty">没有找到符合条件的事件。</div>';
}
function renderEventList() {
  const visible = filteredEvents();
  $("eventList").innerHTML = "";
  if (!visible.length) {
    $("eventList").innerHTML = '<p class="empty">没有符合条件的事件，请更换筛选条件。</p>';
    return;
  }
  visible.forEach(e => {
    const b = document.createElement("button");
    b.className = "secondary";
    b.style.cssText = "display:block;width:100%;text-align:left;margin:5px 0;background:" +
      (selectedEvent && selectedEvent.id === e.id ? "#ead0a0" : "#fff8e8");
    b.innerHTML = '<span style="color:#922f23">' + escapeHTML(e.date) + '</span>　' +
      escapeHTML(e.title) + '<span class="small">　[' + escapeHTML(e.dynasty) + ']</span>';
    b.onclick = () => selectEvent(e);
    $("eventList").appendChild(b);
  });
}
function renderDetail() {
  const e = selectedEvent;
  if (!e) return;
  $("eventDetail").innerHTML = `
    <div class="event-date">${escapeHTML(e.date)} · ${escapeHTML(e.dynasty)}时期</div>
    <div class="event-title">${escapeHTML(e.title)}</div>
    <div>${e.keywords.map(k => '<span class="tag">'+escapeHTML(k)+'</span>').join("")}</div>
    <div class="detail-block"><strong>事件概述</strong><br>${escapeHTML(e.summary)}</div>
    <div class="detail-block"><strong>历史背景</strong><br>${escapeHTML(e.background)}</div>
    <div class="detail-block"><strong>历史影响</strong><br>${escapeHTML(e.impact)}</div>
    <div class="detail-block"><strong>相关人物</strong><br>${escapeHTML(e.people)}</div>
    <div class="small">主题：${escapeHTML(e.topic)}</div>`;
  $("noteEventName").textContent = e.title + "（" + e.date + "）";
  $("eventNote").value = notes[e.id] || "";
  $("noteStatus").textContent = "";
}
function selectEvent(e) {
  selectedEvent = e;
  $("yearSlider").value = Math.max(-2070, Math.min(1912, e.year));
  $("yearDisplay").textContent = yearText(e.year);
  renderAll();
  renderDetail();
}
function renderAll() {
  const y = Number($("yearSlider").value);
  $("yearDisplay").textContent = yearText(y);
  renderTimeline();
  renderEventList();
  const buttons = [...$("dynastyButtons").children];
  buttons.forEach((b, i) => {
    const d = i === 0 ? "all" : dynasties[i-1];
    b.className = ( $("dynastyFilter").value === d ? "active" : "secondary" );
  });
  if (selectedEvent && !filteredEvents().some(e => e.id === selectedEvent.id)) {
    selectedEvent = null;
    $("eventDetail").innerHTML = '<div class="empty">当前筛选条件下没有选中的事件。</div>';
    $("noteEventName").textContent = "尚未选择事件";
    $("eventNote").value = "";
  } else if (selectedEvent) renderDetail();
}
function escapeHTML(value) {
  return String(value ?? "").replace(/[&<>"']/g, c => ({
    "&":"&amp;", "<":"&lt;", ">":"&gt;", '"':"&quot;", "'":"&#39;"
  }[c]));
}
function downloadCSV(filename, rows) {
  const csv = "\uFEFF" + rows.map(row => row.map(v =>
    '"' + String(v ?? "").replace(/"/g, '""') + '"'
  ).join(",")).join("\r\n");
  const blob = new Blob([csv], {type:"text/csv;charset=utf-8;"});
  const url = URL.createObjectURL(blob);
  const a = document.createElement("a");
  a.href = url; a.download = filename;
  document.body.appendChild(a); a.click(); a.remove();
  URL.revokeObjectURL(url);
}
function renderRecords() {
  $("recordHeading").textContent = selectedRecordDynasty + "朝记录簿";
  [...$("recordDynasties").children].forEach((b, i) => {
    b.className = dynasties[i] === selectedRecordDynasty ? "active" : "secondary";
  });
  const list = records[selectedRecordDynasty] || [];
  const tbody = $("recordTableBody");
  tbody.innerHTML = "";
  if (!list.length) {
    tbody.innerHTML = '<tr><td colspan="6">本朝还没有自定义记录，可以在上方添加。</td></tr>';
    return;
  }
  list.forEach((r, index) => {
    const tr = document.createElement("tr");
    [r.date,r.title,r.topic,r.people,r.content].forEach(value => {
      const td = document.createElement("td");
      td.textContent = value || "";
      tr.appendChild(td);
    });
    const td = document.createElement("td");
    const del = document.createElement("button");
    del.textContent = "删除";
    del.onclick = () => {
      if (!confirm("确定删除这条记录吗？")) return;
      records[selectedRecordDynasty].splice(index,1);
      save("huaxia_records", records);
      renderRecords();
    };
    td.appendChild(del); tr.appendChild(td); tbody.appendChild(tr);
  });
}
$("yearSlider").addEventListener("input", () => {
  const y = Number($("yearSlider").value);
  $("yearDisplay").textContent = yearText(y);
  const visible = filteredEvents();
  if (visible.length) {
    const nearest = visible.reduce((best, e) =>
      Math.abs(e.year-y) < Math.abs(best.year-y) ? e : best, visible[0]);
    selectedEvent = nearest;
    renderAll();
  }
});
$("dynastyFilter").addEventListener("change", renderAll);
$("topicFilter").addEventListener("change", renderAll);
$("searchInput").addEventListener("input", renderAll);
$("resetBtn").onclick = () => {
  $("dynastyFilter").value = "all";
  $("topicFilter").value = "all";
  $("searchInput").value = "";
  $("yearSlider").value = -2070;
  selectedEvent = null;
  $("eventDetail").innerHTML = '<div class="empty">请选择时间轴上的历史事件。</div>';
  $("noteEventName").textContent = "尚未选择事件";
  $("eventNote").value = "";
  renderAll();
};
$("saveNoteBtn").onclick = () => {
  if (!selectedEvent) { alert("请先选择一个历史事件。"); return; }
  notes[selectedEvent.id] = $("eventNote").value;
  const ok = save("huaxia_notes", notes);
  $("noteStatus").textContent = ok ? "札记已保存在本浏览器。" : "保存失败，可能是浏览器存储空间不足。";
};
$("clearNoteBtn").onclick = () => {
  if (!selectedEvent) { alert("请先选择一个历史事件。"); return; }
  if (!confirm("确定清空当前事件的札记吗？")) return;
  delete notes[selectedEvent.id];
  save("huaxia_notes", notes);
  $("eventNote").value = "";
  $("noteStatus").textContent = "当前札记已清空。";
};
$("addRecordBtn").onclick = () => {
  const title = $("recordTitle").value.trim();
  if (!title) { alert("请填写事件名称。"); return; }
  if (!records[selectedRecordDynasty]) records[selectedRecordDynasty] = [];
  records[selectedRecordDynasty].push({
    date:$("recordDate").value.trim(),
    title,
    topic:$("recordTopic").value,
    people:$("recordPeople").value.trim(),
    content:$("recordContent").value.trim()
  });
  const ok = save("huaxia_records", records);
  $("recordDate").value = "";
  $("recordTitle").value = "";
  $("recordPeople").value = "";
  $("recordContent").value = "";
  renderRecords();
  if (!ok) alert("保存失败，请检查浏览器存储空间。");
};
$("exportRecordsBtn").onclick = () => {
  const list = records[selectedRecordDynasty] || [];
  downloadCSV(selectedRecordDynasty + "朝记录.csv",
    [["朝代","时间","事件","主题","相关人物","内容"],
      ...list.map(r => [selectedRecordDynasty,r.date,r.title,r.topic,r.people,r.content])]);
};
$("exportAllBtn").onclick = () => {
  const rows = [["朝代","时间","事件","主题","相关人物","内容"]];
  Object.keys(records).forEach(d => (records[d] || []).forEach(r =>
    rows.push([d,r.date,r.title,r.topic,r.people,r.content])));
  downloadCSV("全部朝代记录.csv", rows);
};
$("exportEventsBtn").onclick = () => downloadCSV("中国古代历史事件.csv", [
  ["时间","朝代","事件","主题","相关人物","概述","历史背景","历史影响","关键词"],
  ...events.map(e => [e.date,e.dynasty,e.title,e.topic,e.people,e.summary,e.background,e.impact,e.keywords.join("、")])
]);
$("exportNotesBtn").onclick = () => {
  const rows = [["事件","时间","札记"]];
  events.forEach(e => { if (notes[e.id]) rows.push([e.title,e.date,notes[e.id]]); });
  downloadCSV("历史复习札记.csv", rows);
};

initFilters();
renderAll();
renderRecords();
if (events.length) selectEvent(events[0]);
</script>
</body>
</html>

