<!DOCTYPE htmВаше имя"ru">
<head>
  <Войти<!DOCTYPE htmВаше имя"ru">
<head>
  <metaЗапомнить меня<!DOCTYPE htmВаше имя"ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ModelGo — 3D печать и услуги</title>
  <link rel="stylesheet" href="css/style.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
</head>
<body>
  <nav class="navbar" id="navbar">
    <div class="container nav-container">
      <a href="#" class="logo">
        <i class="fas fa-cube"></i>
        <span>Model<span class="accent">Go</span></span>
      </a>
      <div class="nav-toggle" id="navToggle">
        <span></span><span></span><span></span>
      </div>
      <ul class="nav-menu" id="navMenu">
        <li><a href="#hero" class="nav-link active">Главная</a></li>

        

        <li><a href="#products" class="nav-link">Товары</a></li>
        <li><a href="#calculator" class="nav-link">Калькулятор</a></li>
        <li><a href="#pricing" class="nav-link">Цены</a></li>

        <li id="userInfo" style="display:none">
            <span style="color:var(--text-secondary);font-size:0.9rem;padding:8px 12px">Привет <span id="userName"></span> | <a href="#" onclick="logout()" style="color:var(--accent)">Выйти</a></span>
          </li>
          <li>
          <a href="#cart" class="nav-link cart-link" id="cartLink">
            <i class="fas fa-shopping-cart"></i>
            <span class="cart-badge" id="cartBadge">0</span>
          </a>
        </li>
      </ul>
    </div>
  </nav>

  <section id="hero" class="hero">
    <div class="hero-overlay"></div>
    <div class="container hero-content">
      <div class="hero-text">
        <h1>3D печать <span class="accent">высокого качества</span></h1>

        <div class="hero-buttons">

          
        </div>
      </div>
      <div class="hero-visual">
        <div class="cube-3d">
          <div class="cube-face front"></div>
          <div class="cube-face back"></div>
          <div class="cube-face right"></div>
          <div class="cube-face left"></div>
          <div class="cube-face top"></div>
          <div class="cube-face bottom"></div>
        </div>
      </div>
    </div>
  </section>

  <section id="pricing" class="pricing section">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">Цены</span>
        <h2>Стоимость услуг</h2>
        <p>Прозрачные цены для ваших проектов</p>
      </div>
      <div class="pricing-grid">
                <div class="price-card">
          <div class="price-card-header">
            <span class="price-label">Технология</span>
            <h3>FDM (пластик)</h3>
            <div class="price"><span class="price-value">3</span> ₽/г</div>
          </div>
          <ul class="price-features">
            <li><span class="feature-label">Материал</span> — PLA, PETG</li>
            <li><i class="fas fa-check"></i> Слой 0.05–0.3 мм</li>
          </ul>
        </div>
            </div>
    </div>
  </section>  <section id="calculator" class="calculator section">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">Калькулятор</span>
        <h2>Калькулятор стоимости печати</h2>
        <p>Цена FDM печати: 3 ₽/г</p>
      </div>
      <div class="calc-container">
        <div class="calc-form">
          <div class="form-group">
            <label for="calcTech">Технология</label>
            <select id="calcTech">
              <option value="fdm">FDM (пластик)</option>
              <option value="sla">SLA (смоляной)</option>
              <option value="sls">SLS (порошок)</option>
            </select>
          </div>
          <div class="form-group">
            <label for="calcMaterial">Материал</label>
            <select id="calcMaterial">
              <option value="pla">PLA</option>
              <option value="petg">PETG</option>
              
              
              
            </select>
          </div>
          <div class="form-row">
            <div class="form-group">
              <label for="calcWeight">Вес детали (г)</label>
              <input type="number" id="calcWeight" value="50" min="1" max="5000">
            </div>
            <div class="form-group">
              <label for="calcQuantity">�Количество</label>
              <input type="number" id="calcQuantity" value="1" min="1" max="1000">
            </div>
          </div>
          <div class="form-group">
            <label>Сложность модели</label>
            <div class="radio-group">
              <label class="radio-label">
                <input type="radio" name="complexity" value="simple" checked>
                <span>Простая</span>
              </label>
              <label class="radio-label">
                <input type="radio" name="complexity" value="medium">
                <span>Средняя</span>
              </label>
              <label class="radio-label">
                <input type="radio" name="complexity" value="complex">
                <span>Сложная</span>
              </label>
            </div>
          </div>
          <div class="form-group">
            <label>
              <input type="checkbox" id="calcPostProcessing">Постобработка (шлифовка + покраска)</label>
          </div>
          <button class="btn btn-primary btn-calc" id="calcBtn"Рассчитать</button>
        </div>
        <div class="calc-result" id="calcResult">
          <div class="calc-result-placeholder">
            <i class="fas fa-calculator"></i>
            <p>Введите параметры и нажмите «Рассчитать»</p>
          </div>
          <div class="calc-result-content" id="calcResultContent" style="display:none;">
            <h3>Итого стоимость</h3>
            <div class="calc-breakdown">
              <div class="calc-row"><span>Печать</span><span id="calcPrintCost">0 ₽</span></div>
              <div class="calc-row"><span>Материал</span><span id="calcMatCost">0 ₽</span></div>
              <div class="calc-row" id="calcPostRow" style="display:none;"><span>Постобработка</span><span id="calcPostCost">0 ₽</span></div>
              <div class="calc-row calc-divider"></div>
              <div class="calc-row calc-total"><span>�����</span><span id="calcTotalCost">0 ₽</span></div>
            </div>
            <button class="btn btn-primary" id="calcAddToCart">Добавить в корзину</button>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="cart" class="cart-section section">
    <div class="container">
      <div class="section-header">
        <span class="section-tКорзина</span>
        <h2>Ваш заказ</h2>
        <p>Проверьте и подтвердите заказ</p>
      </div>
      <div class="cart-content" id="cartContent">
        <div class="cart-empty">
          <i class="fas fa-shopping-cart"></i>
          <p>Корзина пуста</p>
          <a href="#products" class="btn btn-primary">Перейти к товарам</a>
        </div>
        <div class="cart-items" id="cartItems" style="display:none;">
          <div class="cart-list" id="cartList"></div>
          <div class="cart-summary">
            <div class="cart-total-row">
              <span>Итого:</span>
              <span id="cartTotal">0 ₽</span>
            </div>
            <button class="btn btn-primary" id="checkoutBtn">�Оформить заказ</button>
            <button class="btn btn-outline" id="clearCartBtn">�Очистить корзину</button>
          </div>
        </div>
      </div>
    </div>
  </section>

    <section id="products" class="products section">
    <div class="container">
      <div class="section-header">
        <span class="section-tТовары</span>
        <h2>Наши товары</h2>
      </div>
      <div class="products-grid" id="productsGrid"></div>
  </section>

    <section id="contacts" class="contacts section">
    <div class="container">
      <div class="section-header">
        <span class="section-tКонтакты</span>
        <h2>Свяжитесь с нами</h2>
        <p>Ответим на вопросы и поможем с заказов</p>
      </div>
      <div class="contacts-grid">
        <div class="contact-info">
          <div class="contact-item">
            <i class="fas fa-clock"></i>
            <div>
              <h4>Режим работы</h4>
              <p>Пн–Пт: 17 – 21:00<br>Сб: 13:00 – 22:00</p>
            </div>
          </div>
        </div>
        <div class="contact-form" id="contactForm">
          <div class="form-group">
            <labelВаше имя</label>
          </div>
          <div class="form-group">
            <span class="contact-static">t03806069@gmail.com</span>
          </div>
          <div class="form-group">
            <span class="contact-static">спасибо за доверие к нам.</span>
          </div>
          <div class="form-group">
            <span class="contact-static">������� �� ������� � ���.</span>
          </div>

        </div>
      </div>
    </div>
  </section>
  <footer class="footer">
    <div class="container footer-content">
      <div class="footer-brand">
        <a href="#" class="logo">
          <i class="fas fa-cube"></i>
          <span>Model<span class="accent">Go</span></span>
        </a>
        <p>Профессиональная 3D печать и услуги. Качественно, быстро, надёжно.</p>
      </div>
      <div class="footer-links">
        <h4>Навигация</h4>
        <ul>
          
          
          
          <li><a href="#products">Товары</a></li>
          <li><a href="#calculator">Калькулятор</a></li>
          <li><a href="#pricing">Цены</a></li>
        </ul>
      </div>
      

    </div>
    <div class="footer-bottom">
      <div class="container">
        <p>&copy; 2026 ModelGo. Все права защищены.</p>
      </div>
    </div>
  </footer>

  <div class="cart-notification" id="cartNotification">
    <i class="fas fa-check-circle"></i>
    <span>Товар добавлен в корзину</span>
  </div>

  <div class="modal" id="orderModal">
    <div class="modal-content">
      <span class="modal-close">&times;</span>
      <div class="modal-body">
        <i class="fas fa-check-circle modal-icon"></i>
        <h2>Заказ оформлен!</h2>
        <p>Мы свяжемся с вами в ближайшее время для подтверждения заказа.</p>
        <button class="btn btn-primary modal-btn">Хорошо</button>
      </div>
    </div>
  </div>

  <script src="js/data.js"></script>
  <script src="js/cart.js"></script>
  <script src="js/calculator.js"></script>
  <script src="js/auth.js"></script>
  <script src="js/products.js"></script>
  <script src="js/script.js"></script>
<div class="modal" id="authModal">
    <div class="modal-content" style="max-width:380px">
      <div class="modal-body">
        <i class="fas fa-user-circle modal-icon" style="font-size:3rem;color:var(--accent)"></i>
        <h2>Добро пожаловать</h2>
        <p style="margin-bottom:20px">Введите ваше имя для входа на сайт
