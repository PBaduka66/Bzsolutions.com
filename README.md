<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SILVA & COSTA SOLUÇÕES, LDA</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
            color: #667eea;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        nav a:hover {
            color: #667eea;
            transform: translateY(-2px);
        }

        nav a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: #667eea;
            transition: width 0.3s ease;
        }

        nav a:hover::after {
            width: 100%;
        }

        .hero {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.9), rgba(118, 75, 162, 0.9));
            color: white;
            padding: 100px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="50" cy="50" r="1" fill="white" opacity="0.1"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
            opacity: 0.3;
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3.5em;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: 1.3em;
            margin-bottom: 30px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            animation: fadeInUp 1s ease 0.2s both;
        }

        .btn {
            display: inline-block;
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            color: white;
            padding: 15px 35px;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
            animation: fadeInUp 1s ease 0.4s both;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
        }

        .section {
            padding: 80px 0;
            background: white;
        }

        .section:nth-child(even) {
            background: #f8f9fa;
        }

        .section-title {
            text-align: center;
            font-size: 2.5em;
            margin-bottom: 50px;
            color: #333;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 2px;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            margin-top: 60px;
        }

        .feature-card {
            background: white;
            padding: 40px 30px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border: 1px solid rgba(102, 126, 234, 0.1);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 2em;
            color: white;
        }

        .stats-section {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 80px 0;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            text-align: center;
        }

        .stat-item {
            padding: 20px;
        }

        .stat-number {
            font-size: 3em;
            font-weight: bold;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .delivery-section {
            background: #f8f9fa;
            padding: 80px 0;
        }

        .delivery-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .delivery-info {
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
        }

        .delivery-info h3 {
            color: #667eea;
            margin-bottom: 20px;
            font-size: 1.5em;
        }

        .delivery-info ul {
            list-style: none;
        }

        .delivery-info li {
            padding: 10px 0;
            border-bottom: 1px solid #eee;
            position: relative;
            padding-left: 30px;
        }

        .delivery-info li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: #28a745;
            font-weight: bold;
        }

        .clients-section {
            background: white;
            padding: 80px 0;
        }

        .clients-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 30px;
            align-items: center;
            margin-top: 50px;
        }

        .client-logo {
            background: #f8f9fa;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .client-logo:hover {
            border-color: #667eea;
            transform: scale(1.05);
        }

        footer {
            background: #333;
            color: white;
            padding: 50px 0 20px;
            text-align: center;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 30px;
        }

        .footer-section h4 {
            margin-bottom: 20px;
            color: #667eea;
        }

        .footer-section p, .footer-section a {
            color: #ccc;
            text-decoration: none;
            line-height: 1.8;
        }

        .footer-section a:hover {
            color: #667eea;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5em;
            }
            
            .delivery-content {
                grid-template-columns: 1fr;
            }
            
            .header-content {
                flex-direction: column;
                gap: 20px;
            }
            
            nav ul {
                gap: 15px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">S&C SOLUÇÕES</div>
                <nav>
                    <ul>
                        <li><a href="#inicio">Início</a></li>
                        <li><a href="#servicos">Serviços</a></li>
                        <li><a href="#sobre">Sobre</a></li>
                        <li><a href="#entrega">Entrega</a></li>
                        <li><a href="#contacto">Contacto</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <section id="inicio" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>PORQUÊ ESCOLHER-NOS</h1>
                <p>Bem-vindo ao nosso Espaço Comercial. Hoje, a empresa orgulha-se de contribuir para o desenvolvimento do mercado, com um compromisso contínuo em adaptar-se às novas exigências e desafios da indústria.</p>
                <a href="#servicos" class="btn">Conheça Nossos Serviços</a>
            </div>
        </div>
    </section>

    <section id="servicos" class="section">
        <div class="container">
            <h2 class="section-title">Metas da Empresa</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">⭐</div>
                    <h3>Excelência no Atendimento</h3>
                    <p>Comprometemo-nos a oferecer um atendimento personalizado e de alta qualidade, superando as expectativas dos nossos clientes em cada interação.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📈</div>
                    <h3>Crescimento Sustentável</h3>
                    <p>Focamos no desenvolvimento contínuo e sustentável, investindo em inovação e melhorias constantes dos nossos processos e serviços.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🏆</div>
                    <h3>Liderança no Mercado</h3>
                    <p>Buscamos ser referência no nosso sector, mantendo-nos na vanguarda das tendências e tecnologias do mercado angolano.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="stats-section">
        <div class="container">
            <h2 class="section-title" style="color: white;">NÚMEROS FALAM</h2>
            <p style="text-align: center; font-size: 1.2em; margin-bottom: 50px;">Porquê contratar a S&C Soluções</p>
            <div class="stats-grid">
                <div class="stat-item">
                    <div class="stat-number" id="areas">1530</div>
                    <p>Áreas estudadas</p>
                </div>
                <div class="stat-item">
                    <div class="stat-number" id="projetos">1247</div>
                    <p>Projectos completos</p>
                </div>
                <div class="stat-item">
                    <div class="stat-number" id="clientes">203</div>
                    <p>Clientes e parceiros</p>
                </div>
                <div class="stat-item">
                    <div class="stat-number" id="ideias">1320</div>
                    <p>Ideias realizadas</p>
                </div>
            </div>
        </div>
    </section>

    <section id="entrega" class="delivery-section">
        <div class="container">
            <h2 class="section-title">REGRAS E CUSTOS</h2>
            <div class="delivery-content">
                <div class="delivery-info">
                    <h3>Entregas ao Domicílio</h3>
                    <p>A Silva & Costa Soluções, Lda oferece o serviço de entrega ao domicílio nas seguintes áreas:</p>
                    <ul>
                        <li>Luanda, fazemos a entrega em todos os bairros da capital</li>
                        <li>Para áreas fora da nossa zona de cobertura padrão, favor entrar em contacto</li>
                    </ul>
                </div>
                <div class="delivery-info">
                    <h3>Prazos de Entrega</h3>
                    <ul>
                        <li>Entrega Local: Entregas dentro de Luanda em até 10 dias úteis</li>
                        <li>Entrega em Outras Regiões: Para outras áreas, prazo de 15 a 25 dias úteis</li>
                        <li>Horário: Segunda a sexta-feira, das 08:00 às 18:00</li>
                        <li>Entregas aos sábados mediante acordo prévio</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <section class="clients-section">
        <div class="container">
            <h2 class="section-title">Nossos Parceiros</h2>
            <div class="clients-grid">
                <div class="client-logo">
                    <h4>Cliente 1</h4>
                    <p>Parceiro Premium</p>
                </div>
                <div class="client-logo">
                    <h4>Cliente 2</h4>
                    <p>Parceiro Estratégico</p>
                </div>
                <div class="client-logo">
                    <h4>Cliente 3</h4>
                    <p>Parceiro de Longa Data</p>
                </div>
                <div class="client-logo">
                    <h4>Cliente 4</h4>
                    <p>Parceiro Institucional</p>
                </div>
                <div class="client-logo">
                    <h4>Cliente 5</h4>
                    <p>Parceiro Tecnológico</p>
                </div>
                <div class="client-logo">
                    <h4>Cliente 6</h4>
                    <p>Parceiro Regional</p>
                </div>
            </div>
        </div>
    </section>

    <footer id="contacto">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h4>Silva & Costa Soluções</h4>
                    <p>Comprometidos com a excelência e inovação no mercado angolano. Juntos construímos o futuro.</p>
                </div>
                <div class="footer-section">
                    <h4>Contactos</h4>
                    <p>Email: info@silvacosta.ao</p>
                    <p>Telefone: +244 xxx xxx xxx</p>
                    <p>Endereço: Luanda, Angola</p>
                </div>
                <div class="footer-section">
                    <h4>Serviços</h4>
                    <p><a href="#servicos">Consultoria</a></p>
                    <p><a href="#servicos">Projectos</a></p>
                    <p><a href="#servicos">Soluções Personalizadas</a></p>
                </div>
            </div>
            <hr style="border: 1px solid #555; margin: 30px 0;">
            <p>&copy; 2025 Silva & Costa Soluções, Lda. Todos os direitos reservados.</p>
        </div>
    </footer>

    <script>
        // Animação dos números
        function animateCounter(id, target) {
            const element = document.getElementById(id);
            let current = 0;
            const increment = target / 50;
            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    current = target;
                    clearInterval(timer);
                }
                element.textContent = Math.floor(current);
            }, 50);
        }

        // Observador para iniciar animação quando a seção estiver visível
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateCounter('areas', 1530);
                    animateCounter('projetos', 1247);
                    animateCounter('clientes', 203);
                    animateCounter('ideias', 1320);
                    observer.unobserve(entry.target);
                }
            });
        });

        observer.observe(document.querySelector('.stats-section'));

        // Scroll suave
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    targetElement.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Efeito de parallax simples no hero
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero');
            if (hero) {
                hero.style.transform = translateY(${scrolled * 0.5}px);
            }
        });
    </script>
</body>
</html>
