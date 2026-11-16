<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ООО «Лайнер» — Пивоваренный завод в Минеральных Водах</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body { font-family: 'Segoe UI', Arial, sans-serif; line-height: 1.6; color: #333; background: #fdfaf5; }

  /* ===== Модальное окно возраста ===== */
  #age-gate {
    position: fixed; inset: 0; z-index: 9999;
    background: rgba(20, 12, 8, 0.95);
    display: flex; align-items: center; justify-content: center;
    padding: 20px;
  }
  #age-gate.hidden { display: none; }
  .age-box {
    background: #fdfaf5; border-radius: 16px; padding: 40px 30px;
    max-width: 440px; width: 100%; text-align: center;
    box-shadow: 0 10px 40px rgba(0,0,0,0.4);
  }
  .age-box .logo-small { font-size: 22px; font-weight: bold; letter-spacing: 2px; color: #2c1810; margin-bottom: 20px; }
  .age-box h3 { font-size: 22px; color: #2c1810; margin-bottom: 12px; }
  .age-box p { font-size: 15px; color: #555; margin-bottom: 25px; }
  .age-buttons { display: flex; gap: 12px; flex-wrap: wrap; justify-content: center; }
  .age-btn {
    flex: 1 1 140px; padding: 14px 20px; border: none; border-radius: 8px;
    font-size: 16px; font-weight: bold; cursor: pointer; transition: 0.2s;
  }
  .age-btn.yes { background: #2c1810; color: #f5e6d3; }
  .age-btn.yes:hover { background: #d4a373; color: #2c1810; }
  .age-btn.no { background: #e0e0e0; color: #555; }
  .age-btn.no:hover { background: #ccc; }
  .age-note { font-size: 12px; color: #888; margin-top: 18px; }
  #age-denied { display: none; }
  #age-denied.show { display: block; }

  /* ===== Основной сайт ===== */
  header { background: #2c1810; color: #f5e6d3; padding: 15px 0; position: sticky; top: 0; z-index: 100; }
  .container { max-width: 1100px; margin: 0 auto; padding: 0 20px; }
  header .container { display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px; }
  .logo { font-size: 26px; font-weight: bold; letter-spacing: 2px; color: #d4a373; }
  nav { display: flex; flex-wrap: wrap; gap: 6px 18px; }
  nav a { color: #f5e6d3; text-decoration: none; font-size: 15px; white-space: nowrap; }
  nav a:hover { color: #d4a373; }
  .hero { background: linear-gradient(rgba(44,24,16,0.85), rgba(44,24,16,0.85)), url('https://images.unsplash.com/photo-1535958636474-b021ee887b13?w=1200') center/cover; color: #fff; padding: 100px 0; text-align: center; }
  .hero h1 { font-size: 42px; margin-bottom: 15px; }
  .hero p { font-size: 18px; opacity: 0.9; max-width: 700px; margin: 0 auto; }
  .badge { display: inline-block; background: #d4a373; color: #2c1810; padding: 8px 20px; border-radius: 30px; font-weight: bold; margin-bottom: 20px; font-size: 14px; }
  .tg-btn {
    display: inline-block; background: #229ED9; color: #fff;
    padding: 12px 28px; border-radius: 8px; text-decoration: none;
    font-weight: bold; font-size: 16px; margin-top: 25px; transition: 0.2s;
  }
  .tg-btn:hover { background: #1a7fb0; }
  section { padding: 70px 0; }
  section:nth-of-type(even) { background: #f9f5f0; }
  h2 { font-size: 32px; margin-bottom: 30px; color: #2c1810; border-left: 5px solid #d4a373; padding-left: 15px; }
  h3.sub { margin-top: 30px; color: #2c1810; font-size: 22px; }
  .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 25px; }
  .card { background: #fff; border-radius: 10px; padding: 30px; box-shadow: 0 4px 15px rgba(0,0,0,0.05); border-top: 4px solid #d4a373; }
  .card h3 { color: #2c1810; margin-bottom: 15px; font-size: 22px; }
  .info-row { display: flex; margin-bottom: 12px; align-items: flex-start; }
  .info-row strong { min-width: 180px; color: #2c1810; }
  .beer-note { background: #fff3cd; border-left: 5px solid #ffc107; padding: 20px; border-radius: 8px; margin: 30px 0; font-size: 15px; }
  footer { background: #2c1810; color: #aaa; padding: 30px 0; text-align: center; font-size: 14px; }
  footer a { color: #d4a373; text-decoration: none; }
  @media (max-width: 600px) {
    .hero h1 { font-size: 28px; }
    nav a { font-size: 14px; }
    .info-row { flex-direction: column; }
    .info-row strong { min-width: auto; }
  }
</style>
</head>
<body>

<!-- ===== Окно подтверждения возраста ===== -->
<div id="age-gate">
  <div class="age-box">
    <div class="logo-small">ЛАЙНЕР</div>

    <div id="age-question">
      <h3>Вам есть 18 лет?</h3>
      <p>Сайт содержит информацию об алкогольной продукции. Подтвердите, что вы достигли совершеннолетия.</p>
      <div class="age-buttons">
        <button class="age-btn yes" onclick="ageConfirm(true)">Да, мне 18+</button>
        <button class="age-btn no" onclick="ageConfirm(false)">Нет, мне меньше 18</button>
      </div>
      <div class="age-note">Нажимая «Да», вы подтверждаете, что вам исполнилось 18 лет.</div>
    </div>

    <div id="age-denied">
      <h3>Доступ ограничен</h3>
      <p>К сожалению, сайт доступен только для лиц старше 18 лет. Вы можете закрыть эту страницу.</p>
    </div>
  </div>
</div>

<header>
  <div class="container">
    <div class="logo">ЛАЙНЕР</div>
    <nav>
      <a href="#company">Компания</a>
      <a href="#products">Продукция</a>
      <a href="#production">Производство</a>
      <a href="#partners">Партнёрам</a>
      <a href="#where">Где купить?</a>
      <a href="#contacts">Контакты</a>
    </nav>
  </div>
</header>

<div class="hero">
  <div class="container">
    <div class="badge">С 1997 года</div>
    <h1>Пивоваренный завод «Лайнер»</h1>
    <p>Производство пива в Минеральных Водах. Классические сорта, небольшие партии, внимание к качеству.</p>
    <a href="https://t.me/laynercraft" target="_blank" rel="noopener" class="tg-btn">Мы в Telegram</a>
  </div>
</div>

<section id="company">
  <div class="container">
    <h2>Компания</h2>
    <p>ООО «Лайнер» — пивоваренное предприятие, расположенное в городе Минеральные Воды Ставропольского края. Завод основан в 1997 году и на протяжении более чем двадцати пяти лет специализируется на производстве пива.</p>
    <p style="margin-top:15px;">Как микропредприятие, мы сохраняем гибкость небольших партий производства, уделяя особое внимание контролю качества и соблюдению традиционных технологий пивоварения. Наша продукция выпускается на собственных производственных мощностях и поставляется преимущественно в регионе Кавказских Минеральных Вод.</p>
  </div>
</section>

<section id="products">
  <div class="container">
    <h2>Продукция</h2>
    <p>Завод «Лайнер» производит пиво в кегах объёмом 30 литров. Ассортимент включает светлое непастеризованное фильтрованное пиво и безалкогольное пиво. Актуальный ассортимент и наличие уточняйте по телефону.</p>
    <div class="grid" style="margin-top:25px;">
      <div class="card">
        <h3>Пиво светлое</h3>
        <p>Непастеризованное фильтрованное. Классический солодовый вкус с хмелевой горечью. Поставка в кегах 30 л.</p>
      </div>
      <div class="card">
        <h3>Пиво безалкогольное</h3>
        <p>Светлое фильтрованное, содержание алкоголя до 0.5%. Освежающий вкус для тех, кто за рулём. Кеги 30 л.</p>
      </div>
      <div class="card">
        <h3>Условия хранения</h3>
        <p>Требуется охлаждение. Срок годности — 30 дней. Хранить в сухом, чистом, вентилируемом помещении.</p>
      </div>
    </div>
    <div class="beer-note">
      <strong>⚠️ Важно:</strong> Сайт носит информационный характер. Онлайн-продажа и доставка алкогольной продукции физическим лицам запрещена законодательством РФ.
    </div>
  </div>
</section>

<section id="production">
  <div class="container">
    <h2>Производство</h2>
    <p>Производственная площадка завода «Лайнер» расположена по адресу: г. Минеральные Воды, ул. Дружбы. Предприятие располагает полным циклом пивоварения — от подготовки солода до брожения и фильтрации.</p>
    <p style="margin-top:15px;">Мы придерживаемся классической технологии: используем пивоваренный ячменный солод, хмель и дрожжи, выпуская непастеризованное фильтрованное пиво. Продукция поставляется в кегах объёмом 30 литров, что обеспечивает свежесть напитка при условии соблюдения требуемого температурного режима. Небольшие объёмы производства позволяют нам поддерживать стабильность вкуса от партии к партии.</p>
  </div>
</section>

<section id="partners">
  <div class="container">
    <h2>Партнёрам</h2>
    <p>Мы открыты к сотрудничеству с магазинами, барами, ресторанами и другими предприятиями региона Кавказских Минеральных Вод.</p>
    <p style="margin-top:15px;">По вопросам сотрудничества свяжитесь с нами по телефону или email — обсудим условия и объёмы поставок.</p>
  </div>
</section>

<section id="where">
  <div class="container">
    <h2>Где купить?</h2>
    <p>Нашу продукцию можно приобрести в фирменных магазинах:</p>
    <div class="grid" style="margin-top:25px;">
      <div class="card">
        <h3>Минеральные Воды</h3>
        <p>ул. Дружбы, 41-А<br>Ежедневно, 10:00–22:00</p>
      </div>
      <div class="card">
        <h3>Минеральные Воды</h3>
        <p>ул. Железноводская, 24<br>Ежедневно, 10:00–22:00</p>
      </div>
      <div class="card">
        <h3>Пятигорск</h3>
        <p>ул. Первомайская, 165<br>Ежедневно, 10:00–22:00</p>
      </div>
      <div class="card">
        <h3>Иноземцево</h3>
        <p>ул. Степная, 11<br>Ежедневно, 10:00–22:00</p>
      </div>
    </div>
    <div class="beer-note">
      <strong>⚠️ Важно:</strong> Онлайн-заказ и доставка алкоголя физическим лицам через сайт не осуществляются.
    </div>
  </div>
</section>

<section id="contacts">
  <div class="container">
    <h2>Контакты и реквизиты</h2>
    <div class="info-row"><strong>ООО «Лайнер»</strong></div>
    <div class="info-row"><strong>ИНН:</strong> <span>2630022046</span></div>
    <div class="info-row"><strong>ОГРН:</strong> <span>1022601452565</span></div>
    <div class="info-row"><strong>Юридический адрес:</strong> <span>357210, Ставропольский край, г. Минеральные Воды, ул. Дружбы, д. 41</span></div>
    <div class="info-row"><strong>Телефон:</strong> <span><a href="tel:+78792253054">+7 (87922) 5-30-54</a></span></div>
    <div class="info-row"><strong>Email:</strong> <span><a href="mailto:layner2000@yandex.ru">layner2000@yandex.ru</a></span></div>
    <div class="info-row"><strong>Telegram:</strong> <span><a href="https://t.me/laynercraft" target="_blank" rel="noopener">@laynercraft</a></span></div>

    <h3 class="sub">Фирменные магазины</h3>
    <div class="info-row"><strong>Минеральные Воды:</strong> <span>ул. Дружбы, 41-А (10:00–22:00)</span></div>
    <div class="info-row"><strong>Минеральные Воды:</strong> <span>ул. Железноводская, 24 (10:00–22:00)</span></div>
    <div class="info-row"><strong>Пятигорск:</strong> <span>ул. Первомайская, 165 (10:00–22:00)</span></div>
    <div class="info-row"><strong>Иноземцево:</strong> <span>ул. Степная, 11 (10:00–22:00)</span></div>
    <div class="info-row"><strong>Телефон магазина:</strong> <span><a href="tel:+79289683269">+7 (928) 968-32-69</a></span></div>
  </div>
</section>

<footer>
  <div class="container">
    <p>© 2026 ООО «Лайнер». ИНН 2630022046. Производство пива.</p>
    <p style="margin-top:8px; font-size:12px;">Сайт не является интернет-магазином. Продажа алкоголя дистанционным способом запрещена.</p>
  </div>
</footer>

<script>
  document.addEventListener('DOMContentLoaded', function () {
    var confirmed = localStorage.getItem('layner_age_confirmed');
    if (confirmed === 'yes') {
      document.getElementById('age-gate').classList.add('hidden');
    }
  });

  function ageConfirm(isAdult) {
    if (isAdult) {
      localStorage.setItem('layner_age_confirmed', 'yes');
      document.getElementById('age-gate').classList.add('hidden');
    } else {
      document.getElementById('age-question').style.display = 'none';
      document.getElementById('age-denied').classList.add('show');
    }
  }
</script>

</body>
</html>
