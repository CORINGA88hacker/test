firebase.auth().onAuthStateChanged(user => {
  if (user) {
    carregarFilmes();
    carregarSeries();
    carregarUsuarios();
  } else {
    window.location.href = "login.html";
  }
});

function carregarFilmes() {
  const lista = document.getElementById('listaFilmes');
  firebase.database().ref("filmes").once("value").then(snapshot => {
    lista.innerHTML = '';
    snapshot.forEach(child => {
      const data = child.val();
      const li = document.createElement('li');
      li.textContent = data.titulo || 'Filme sem título';
      lista.appendChild(li);
    });
  });
}

function carregarSeries() {
  const lista = document.getElementById('listaSeries');
  firebase.database().ref("series").once("value").then(snapshot => {
    lista.innerHTML = '';
    snapshot.forEach(child => {
      const data = child.val();
      const li = document.createElement('li');
      li.textContent = data.titulo || 'Série sem título';
      lista.appendChild(li);
    });
  });
}

function carregarUsuarios() {
  const lista = document.getElementById('listaUsuarios');
  firebase.database().ref("users").once("value").then(snapshot => {
    lista.innerHTML = '';
    snapshot.forEach(child => {
      const data = child.val();
      const li = document.createElement('li');
      li.textContent = data.email || 'Usuário sem email';
      lista.appendChild(li);
    });
  });
}
