// Alternar tema claro/escuro
const temaBotao = document.getElementById('tema-toggle');
temaBotao.addEventListener('click', () => {
    document.body.classList.toggle('dark');
});

// Menu responsivo
const menuToggle = document.getElementById('menu-toggle');
const menu = document.querySelector('nav ul.menu');
menuToggle.addEventListener('click', () => {
    menu.classList.toggle('show');
});

// Validação do formulário
const form = document.getElementById('formContato');
form.addEventListener('submit', function(e) {
    e.preventDefault();

    const nome = document.getElementById('nome').value.trim();
    const email = document.getElementById('email').value.trim();
    const mensagem = document.getElementById('mensagem').value.trim();

    if (!nome || !email || !mensagem) {
        alert('Por favor, preencha todos os campos!');
        return;
    }

    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!emailRegex.test(email)) {
        alert('Por favor, insira um e-mail válido!');
        return;
    }

    // Simulação de envio
    form.reset();
    const sucesso = document.getElementById('mensagem-sucesso');
    sucesso.style.display = 'block';
    setTimeout(() => {
        sucesso.style.display = 'none';
    }, 3000);
});
