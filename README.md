<!DOCTYPE html><html lang="fr">
<head><meta charset="UTF-8"><title>Scanne & Devine — Masque</title>
<style>body{font-family:sans-serif;background:#f5f5f5;padding:20px;} .qcm{background:#fff;padding:15px;border-radius:8px;max-width:400px;margin:auto;} button{margin-top:10px;}</style>
</head><body>
<h1>♻️ Déchet : Masque</h1>
<div class="qcm">
  <div id="question"></div>
  <form id="form"></form>
  <button onclick="loadQuestion()">Nouvelle question</button>
</div>
<script>
const Q = [
  {q:"Que devient un masque recyclé ?", a:["Tapis de sol","Blocs de béton","Désinfectant"], c:2},
  {q:"Pourquoi ne pas jeter ton masque sur la voie publique ?", a:["Risques infectieux","Ça sent mauvais","Ça prune localement"], c:0},
  // Ajoute 18 autres...
];
function loadQuestion(){
  const i=Math.floor(Math.random()*Q.length), o=Q[i];
  document.getElementById("form").innerHTML=`
    <p>${o.q}</p>
    ${o.a.map((t,j)=>`<label><input name="c" type="radio" value="${j}"> ${t}</label><br>`).join('')}
    <button type="button" onclick="showAnswer(${o.c})">Voir réponse</button>
  `;
}
function showAnswer(c){
  const sel = document.querySelector('input[name="c"]:checked');
  alert(sel ? (sel.value==c ? "✅ Bonne réponse!" : "❌ Raté...") : "Choisis une réponse.");
}
window.onload=loadQuestion;
</script>
</body></html>
