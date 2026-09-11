# Biblioteca-digital
Biblioteca digital 11-C
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Biblioteca Digital Escolar</title>
<style>
:root{--navy:#163b70;--blue:#2f68c7;--pink:#f4a8ce;--light:#f7f9fc;--text:#1e2b3c;--muted:#6d7888;--white:#fff;--border:#e3e8ef}
*{box-sizing:border-box}body{margin:0;font-family:Arial,Helvetica,sans-serif;background:var(--light);color:var(--text)}
header{height:72px;background:#fff;border-bottom:1px solid var(--border);display:flex;align-items:center;justify-content:space-between;padding:0 6%;position:sticky;top:0;z-index:10}
.brand{display:flex;align-items:center;gap:12px;font-weight:800;color:var(--navy);font-size:19px}.logo{width:42px;height:42px;border-radius:12px;background:linear-gradient(135deg,#f6b5d5,#d9c4ff);display:grid;place-items:center;font-size:23px}
nav{display:flex;gap:24px;align-items:center}nav a{color:var(--navy);text-decoration:none;font-size:14px;cursor:pointer}nav a.active{font-weight:800}.login{background:var(--navy);color:white!important;padding:11px 18px;border-radius:22px}
.hero{padding:64px 8%;display:flex;align-items:center;justify-content:space-between;gap:40px;background:linear-gradient(120deg,#fff 0%,#fff7fb 55%,#f0e9ff 100%);min-height:390px}
.hero h1{font-size:46px;line-height:1.05;margin:0 0 18px;color:var(--navy)}.hero p{font-size:18px;line-height:1.6;color:var(--muted);max-width:590px}.hero-buttons{display:flex;gap:12px;margin-top:25px}.btn{border:0;padding:13px 22px;border-radius:25px;background:var(--navy);color:#fff;font-weight:700;cursor:pointer}.btn.alt{background:#fff;color:var(--navy);border:1px solid var(--navy)}
.illustration{width:370px;height:250px;border-radius:28px;background:#fff;box-shadow:0 20px 45px #263d5b22;display:flex;align-items:center;justify-content:center;font-size:95px}
.section{padding:42px 8%}.section h2{color:var(--navy);margin:0 0 24px}.categories{display:grid;grid-template-columns:repeat(4,1fr);gap:15px}.cat{padding:24px;background:#fff;border:1px solid var(--border);border-radius:18px;cursor:pointer;transition:.2s}.cat:hover{transform:translateY(-3px);box-shadow:0 10px 25px #1c3c5b12}.cat .ico{font-size:30px;margin-bottom:12px}.cat strong{display:block}.cat span{color:var(--muted);font-size:13px}
.resource-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:18px}.card{background:#fff;border:1px solid var(--border);border-radius:18px;overflow:hidden}.cover{height:145px;background:linear-gradient(135deg,#dcecff,#f8d9ea);display:grid;place-items:center;font-size:48px}.card-body{padding:17px}.tag{display:inline-block;background:#eef3ff;color:var(--blue);padding:5px 9px;border-radius:12px;font-size:11px;margin-bottom:8px}.card h3{font-size:16px;margin:5px 0}.card p{font-size:13px;color:var(--muted);min-height:38px}.card button{width:100%;padding:10px;border:0;border-radius:12px;background:var(--navy);color:white;cursor:pointer;font-weight:700}
.app{display:none}.app.active{display:block}.appbar{padding:28px 8%;background:#fff;border-bottom:1px solid var(--border)}.search{display:flex;gap:10px;max-width:800px}.search input{flex:1;padding:15px 18px;border:1px solid var(--border);border-radius:14px;font-size:15px}.filterbar{display:flex;gap:10px;margin:22px 0;flex-wrap:wrap}.filter{padding:9px 14px;border:1px solid var(--border);background:#fff;border-radius:18px;cursor:pointer}.filter.selected{background:var(--navy);color:#fff}
.reader{max-width:1000px;margin:40px auto;background:#fff;border:1px solid var(--border);border-radius:20px;box-shadow:0 12px 30px #182c4514;min-height:540px;padding:55px}.reader h1{text-align:center;color:var(--navy);font-size:34px}.reader .bookpage{margin:35px auto;max-width:650px;line-height:1.8;font-family:Georgia,serif;font-size:17px}.toolbar{display:flex;justify-content:flex-end;gap:10px}.toolbar button{border:0;background:var(--navy);color:#fff;padding:10px 16px;border-radius:10px;cursor:pointer}
.info{display:grid;grid-template-columns:1fr 1fr;gap:22px}.info-box{background:#fff;padding:25px;border:1px solid var(--border);border-radius:18px}.info-box h3{color:var(--navy)}.qr-demo{font-size:110px;text-align:center;padding:20px;background:#fff;border-radius:20px}
footer{background:var(--navy);color:#fff;padding:35px 8%;margin-top:40px}footer p{opacity:.8}
.empty{padding:45px;text-align:center;color:var(--muted);background:#fff;border-radius:18px}
@media(max-width:850px){nav a:not(.login){display:none}.hero{flex-direction:column;text-align:center}.illustration{width:100%;height:210px}.categories,.resource-grid{grid-template-columns:repeat(2,1fr)}.info{grid-template-columns:1fr}}
@media(max-width:500px){.hero h1{font-size:35px}.categories,.resource-grid{grid-template-columns:1fr}.section{padding:32px 5%}.hero{padding:45px 5%}}
</style>
</head>
<body>

<header>
  <div class="brand"><div class="logo">📖</div>Biblioteca Digital Escolar</div>
  <nav>
    <a class="active" onclick="show('home',this)">Inicio</a>
    <a onclick="show('explore',this)">Explorar</a>
    <a onclick="show('about',this)">Proyecto</a>
    <a class="login" onclick="alert('Demo: el inicio de sesión sería implementado para administradores y usuarios de la institución.')">Iniciar sesión</a>
  </nav>
</header>

<main id="home" class="app active">
<section class="hero">
  <div>
    <h1>Tu biblioteca,<br>siempre a un clic</h1>
    <p>Encuentra libros, guías y materiales educativos de forma rápida y sencilla. Accede desde un computador o celular mediante la plataforma o los códigos QR ubicados en la institución.</p>
    <div class="hero-buttons"><button class="btn" onclick="show('explore')">Explorar recursos</button><button class="btn alt" onclick="show('about')">Conocer el proyecto</button></div>
  </div>
  <div class="illustration">📚💻</div>
</section>

<section class="section">
<h2>Explora por áreas</h2>
<div class="categories">
  <div class="cat" onclick="filterArea('Libros')"><div class="ico">📚</div><strong>Libros</strong><span>Lecturas y textos</span></div>
  <div class="cat" onclick="filterArea('Ciencias')"><div class="ico">🔬</div><strong>Ciencias</strong><span>Biología y Química</span></div>
  <div class="cat" onclick="filterArea('Matemáticas')"><div class="ico">🧮</div><strong>Matemáticas</strong><span>Guías y ejercicios</span></div>
  <div class="cat" onclick="filterArea('Inglés')"><div class="ico">🇬🇧</div><strong>Inglés</strong><span>Material de apoyo</span></div>
  <div class="cat" onclick="filterArea('Lengua Castellana')"><div class="ico">📝</div><strong>Lengua Castellana</strong><span>Guías y literatura</span></div>
  <div class="cat" onclick="filterArea('Sociales')"><div class="ico">🌎</div><strong>Sociales</strong><span>Historia y sociedad</span></div>
  <div class="cat" onclick="filterArea('ICFES')"><div class="ico">🎓</div><strong>Material para ICFES</strong><span>Preparación académica</span></div>
  <div class="cat" onclick="show('explore')"><div class="ico">🔎</div><strong>Todos los recursos</strong><span>Ver catálogo completo</span></div>
</div>
</section>

<section class="section">
<h2>Recursos recomendados</h2>
<div id="recommended" class="resource-grid"></div>
</section>
</main>

<main id="explore" class="app">
<div class="appbar">
<h1 style="color:var(--navy)">Explorar biblioteca</h1>
<div class="search"><input id="searchInput" placeholder="Buscar libros, temas o autores..." oninput="renderResources()"><button class="btn" onclick="renderResources()">Buscar</button></div>
<div class="filterbar" id="filters"></div>
</div>
<section class="section"><div id="resources" class="resource-grid"></div></section>
</main>

<main id="reader" class="app">
<div class="reader">
<div class="toolbar"><button onclick="show('explore')">← Volver</button><button onclick="alert('En un proyecto real, aquí se descargaría el archivo autorizado.')">⬇ Descargar</button></div>
<h1 id="readerTitle">Recurso educativo</h1>
<div class="bookpage" id="readerText"></div>
</div>
</main>

<main id="about" class="app">
<section class="section">
<h1 style="color:var(--navy)">Sobre el proyecto</h1>
<p style="color:var(--muted);max-width:800px;line-height:1.7">La Biblioteca Digital Escolar es una propuesta tecnológica de grado 11° para facilitar la consulta de libros, guías y materiales educativos, organizándolos en una plataforma sencilla y accesible mediante enlaces y códigos QR.</p>
<div class="info">
<div class="info-box"><h3>🎯 Objetivo</h3><p>Desarrollar una biblioteca digital que permita organizar y consultar materiales educativos de manera rápida y sencilla.</p><h3>👥 Beneficiarios</h3><p>Estudiantes, docentes, personal de biblioteca y comunidad educativa.</p><h3>📈 Meta inicial</h3><p>Crear un catálogo de mínimo <strong>50 recursos</strong> educativos organizados y accesibles.</p></div>
<div class="info-box"><h3>📱 Acceso por QR</h3><div class="qr-demo">▦</div><p style="text-align:center">En el proyecto real, cada código QR podrá dirigir directamente a la biblioteca o a una sección específica.</p></div>
<div class="info-box"><h3>✨ Beneficios</h3><ul><li>Reduce el tiempo de búsqueda.</li><li>Organiza los recursos.</li><li>Permite acceso desde celulares y computadores.</li><li>Facilita la actualización del catálogo.</li><li>Promueve el uso responsable de la tecnología.</li></ul></div>
<div class="info-box"><h3>💰 Presupuesto</h3><p>Estimado: <strong>$30.000 COP</strong>, principalmente para impresión de afiches, códigos QR y señalización.</p><h3>🗓️ Implementación</h3><p>Investigación → diseño → desarrollo → pruebas → implementación → evaluación.</p></div>
</div>
</section>
</main>

<footer><strong>Biblioteca Digital Escolar</strong><p>IED Ciudadela 20 de Julio · Proyecto tecnológico · Grado 11°</p><p>“La tecnología al servicio del aprendizaje.”</p></footer>

<script>
const data=[
 {t:"Biología – Guía de aprendizaje",a:"Ciencias",g:"Grado 10°",i:"🌿",d:"Guía completa de temas principales de biología."},
 {t:"Biología celular",a:"Ciencias",g:"Grado 11°",i:"🧬",d:"Resumen y esquemas sobre la célula."},
 {t:"Ecosistemas y biodiversidad",a:"Ciencias",g:"Grado 10°",i:"🌳",d:"Material de apoyo con actividades y ejemplos."},
 {t:"Laboratorio de biología",a:"Ciencias",g:"Grado 11°",i:"🧪",d:"Guía para el desarrollo de prácticas de laboratorio."},
 {t:"Matemáticas – Guía de ejercicios",a:"Matemáticas",g:"Grado 11°",i:"📐",d:"Ejercicios de funciones, sucesiones y análisis."},
 {t:"Inglés – Reading practice",a:"Inglés",g:"Grado 11°",i:"🇬🇧",d:"Material de comprensión de lectura."},
 {t:"Historia de Colombia",a:"Sociales",g:"Grado 11°",i:"🌎",d:"Material de consulta sobre procesos históricos."},
 {t:"Lengua Castellana – Literatura",a:"Lengua Castellana",g:"Grado 11°",i:"📖",d:"Guía de literatura y comprensión textual."},
 {t:"Preparación ICFES – Ciencias",a:"ICFES",g:"Grado 11°",i:"🎓",d:"Material de práctica académica."},
 {t:"Química – Conceptos básicos",a:"Ciencias",g:"Grado 10°",i:"⚗️",d:"Guía introductoria de química."}
];
let current="Todos";
function show(id,el){
 document.querySelectorAll('.app').forEach(x=>x.classList.remove('active'));
 document.getElementById(id).classList.add('active');
 if(el){document.querySelectorAll('nav a').forEach(x=>x.classList.remove('active'));el.classList.add('active')}
 if(id==="explore")renderResources();
 window.scrollTo(0,0);
}
function filterArea(a){current=a;show('explore');renderFilters();renderResources();}
function renderFilters(){
 const areas=["Todos","Libros","Ciencias","Matemáticas","Inglés","Lengua Castellana","Sociales","ICFES"];
 document.getElementById("filters").innerHTML=areas.map(a=>`<button class="filter ${current===a?'selected':''}" onclick="current='${a}';renderFilters();renderResources()">${a}</button>`).join("");
}
function card(x){
 return `<div class="card"><div class="cover">${x.i}</div><div class="card-body"><span class="tag">${x.a} · ${x.g}</span><h3>${x.t}</h3><p>${x.d}</p><button onclick="openResource('${x.t.replace(/'/g,"\\'")}')">Ver recurso</button></div></div>`;
}
function renderResources(){
 const q=(document.getElementById("searchInput")?.value||"").toLowerCase();
 let arr=data.filter(x=>(current==="Todos"||x.a===current||current==="Libros") && (x.t+" "+x.a+" "+x.d).toLowerCase().includes(q));
 document.getElementById("resources").innerHTML=arr.length?arr.map(card).join(""):`<div class="empty">No encontramos recursos con esa búsqueda.</div>`;
}
function openResource(title){
 const x=data.find(z=>z.t===title)||data[0];
 document.getElementById("readerTitle").textContent=x.t;
 document.getElementById("readerText").innerHTML=`<p><strong>Área:</strong> ${x.a} &nbsp; | &nbsp; <strong>${x.g}</strong></p><p>${x.d}</p><hr><p>Este espacio representa el visor del recurso. En la versión final de la biblioteca se incorporaría aquí el documento o enlace autorizado para su consulta.</p><p><strong>Información del recurso</strong></p><ul><li>Nombre: ${x.t}</li><li>Área: ${x.a}</li><li>Acceso: consulta digital</li><li>Estado: disponible para demostración</li></ul>`;
 show('reader');
}
document.getElementById("recommended").innerHTML=data.slice(0,4).map(card).join("");
renderFilters();
</script>
</body>
</html>
