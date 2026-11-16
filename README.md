<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ООО «Лайнер» — Пивоваренный завод в Минеральных Водах</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body { font-family: 'Segoe UI', Arial, sans-serif; line-height: 1.6; color: #333; background: #fdfaf5; }
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
  section { padding: 70px 0; }
  section:nth-of-type(even) { background: #f9f5f0; }
  h2 { font-size: 32px; margin-bottom: 30px; color: #2c1810; border-left: 5px solid #d4a373; padding-left: 15px; }
  .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 25px; }
  .card { background: #fff; border-radius: 10px; padding: 30px; box-shadow: 0 4px 15px rgba(0,0,0,0.05); border-top: 4px solid #d4a373; }
  .card h3 { color: #2c1810; margin-bottom: 15px; font-size: 22px; }
  .info-row { display: flex; margin-bottom: 12px; align-items: flex-start; }
  .info-row strong { min-width: 160px; color: #2c1810; }
  .beer-note { background: #fff3cd; border-left: 5px solid #ffc107; padding: 20px; border-radius: 8px; margin: 30px 0; font-size: 15px; }
  footer { background: #2c1810; color: #aaa; padding: 30px 0; text-align: center; font-size: 14px; }
  footer a { color: #d4a373; text-decoration: none; }
  @media (max-width: 600px) { .hero h1 { font-size: 28px; } nav a { font-size: 14px; } }
</style>
</head>
<body>

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
  </div>
</div>

<section id="company">
  <div class="container">
    <h2>Компания</h2>
    <p>ООО «Лайнер» — действующее пивоваренное производство, зарегистрированное в 1997 году. Мы варим пиво небольшими партиями, уделяя внимание качеству и классической технологии.</p>
    <p style="margin-top:15px;">Предприятие работает на рынке более 25 лет, обеспечивая свежей продукцией жителей и гостей региона Кавказских Минеральных Вод.</p>
  </div>
</section>

<section id="products">
  <div class="container">
    <h2>Продукция</h2>
    <div class="grid">
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
    <p>Наше производство расположено в г. Минеральные Воды. Мы используем классическую технологию пивоварения: дробление солода, затирание, фильтрация, кипячение с хмелем, брожение и дображивание.</p>
    <p style="margin-top:15px;">Пиво выпускается непастеризованным и фильтрованным, поставляется в кегах 30 литров. Небольшие объёмы производства позволяют контролировать качество на каждом этапе.</p>
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
    <p>Приобрести нашу продукцию можно:</p>
    <div class="grid" style="margin-top:25px;">
      <div class="card">
        <h3>Напрямую у завода</h3>
        <p>По адресу: г. Минеральные Воды, ул. Дружбы, д. 41. Уточните наличие по телефону.</p>
      </div>
      <div class="card">
        <h3>В магазинах региона</h3>
        <p>Продукция представлена в торговых точках Кавказских Минеральных Вод. Список точек уточняйте по телефону.</p>
      </div>
      <div class="card">
        <h3>Для организаций</h3>
        <p>Поставки в кегах 30 л для баров и магазинов — по договору. Контакты для связи — в разделе «Контакты».</p>
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
    <div class="info-row"><strong>Адрес:</strong> <span>357210, Ставропольский край, г. Минеральные Воды, ул. Дружбы, д. 41</span></div>
    <div class="info-row"><strong>Телефон:</strong> <span><a href="tel:+78792253054">+7 (87922) 5-30-54</a></span></div>
    <div class="info-row"><strong>Email:</strong> <span><a href="mailto:layner2000@yandex.ru">layner2000@yandex.ru</a></span></div>
    <div class="info-row"><strong>Режим работы:</strong> <span>Пн–Пт, 08:00–17:00 (обед 12:00–13:00)</span></div>
  </div>
</section>

<footer>
  <div class="container">
    <p>© 2026 ООО «Лайнер». ИНН 2630022046. Производство пива.</p>
    <p style="margin-top:8px; font-size:12px;">Сайт не является интернет-магазином. Продажа алкоголя дистанционным способом запрещена.</p>
  </div>
</footer>

</body>
</html># -
Пивоваренный завод
