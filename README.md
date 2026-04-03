# Best
Must visit 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>FitZone Gym</title>

<!-- Google Font -->
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&display=swap" rel="stylesheet">

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:'Poppins',sans-serif;
}

body{
  color:white;
  overflow-x:hidden;
}

/* 3D canvas */
#bg{
  position:fixed;
  top:0;
  left:0;
  z-index:-1;
}

/* Navbar */
nav{
  display:flex;
  justify-content:space-between;
  padding:20px;
  background:rgba(0,0,0,0.5);
  position:sticky;
  top:0;
}

nav h1{
  color:#00ffcc;
}

nav ul{
  display:flex;
  gap:20px;
  list-style:none;
}

nav ul li{
  cursor:pointer;
}

/* Hero */
.hero{
  height:100vh;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  text-align:center;
}

.hero h2{
  font-size:3rem;
}

.hero p{
  margin-top:10px;
}

/* Section */
section{
  padding:60px 20px;
  background:rgba(0,0,0,0.7);
}

/* Services */
.services{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
  gap:20px;
}

.card{
  background:#111;
  padding:20px;
  border-radius:10px;
  transition:0.3s;
}

.card:hover{
  transform:scale(1.1);
  background:#00ffcc;
  color:black;
}

/* Contact */
.contact{
  text-align:center;
}

button{
  padding:10px 20px;
  border:none;
  background:#00ffcc;
  cursor:pointer;
  border-radius:5px;
}

footer{
  text-align:center;
  padding:20px;
  background:black;
}
</style>
</head>

<body>

<canvas id="bg"></canvas>

<nav>
  <h1>FitZone</h1>
  <ul>
    <li>Home</li>
    <li>Services</li>
    <li>Contact</li>
  </ul>
</nav>

<div class="hero">
  <h2>Transform Your Body</h2>
  <p>Join the best gym in your city</p>
</div>

<section>
  <h2 style="text-align:center;">Our Services</h2>

  <div class="services">

    <div class="card">Gym Training</div>
    <div class="card">Aerobics</div>
    <div class="card">Crossfit</div>
    <div class="card">Cycling</div>
    <div class="card">Dance Fitness</div>
    <div class="card">HIIT Classes</div>
    <div class="card">Nutrition Consulting</div>
    <div class="card">Personal Training</div>
    <div class="card">Weight Training</div>
    <div class="card">Zumba</div>

    <!-- Extra -->
    <div class="card">Yoga Classes</div>
    <div class="card">Strength Conditioning</div>
    <div class="card">Body Transformation</div>
    <div class="card">Online Coaching</div>

  </div>
</section>

<section class="contact">
  <h2>Contact Us</h2>
  <p>Call Now: 9310290419</p>
  <p>Email: pradeepji896617@gmail.com</p>
  <button>Join Now</button>
</section>

<footer>
  <p>© 2026 FitZone Gym</p>
</footer>

<!-- THREE JS -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r134/three.min.js"></script>

<script>
// Scene
const scene = new THREE.Scene();

// Camera
const camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);

// Renderer
const renderer = new THREE.WebGLRenderer({
  canvas: document.querySelector('#bg'),
});

renderer.setSize(window.innerWidth, window.innerHeight);
camera.position.z = 5;

// Geometry
const geometry = new THREE.TorusKnotGeometry(1, 0.3, 100, 16);
const material = new THREE.MeshStandardMaterial({
  color: 0x00ffcc,
  wireframe: true,
});

const torus = new THREE.Mesh(geometry, material);
scene.add(torus);

// Light
const light = new THREE.PointLight(0xffffff);
light.position.set(5,5,5);
scene.add(light);

// Animation
function animate(){
  requestAnimationFrame(animate);

  torus.rotation.x += 0.01;
  torus.rotation.y += 0.01;

  renderer.render(scene, camera);
}

animate();

// Resize Fix
window.addEventListener('resize', ()=>{
  camera.aspect = window.innerWidth / window.innerHeight;
  camera.updateProjectionMatrix();
  renderer.setSize(window.innerWidth, window.innerHeight);
});
</script>

</body>
</html>
