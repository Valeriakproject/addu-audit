# Шаблон: Cookie-баннер

## Текст баннера

```text
Мы используем cookie-файлы для работы сайта{{#if HAS_REGISTRATION}}, авторизации{{/if}}{{#if HAS_CART}}, корзины{{/if}} и {{#if yandex_metrika_counter}}анализа посещаемости (Яндекс.Метрика){{else}}сбора обезличенной статистики посещаемости{{/if}}. Продолжая использовать сайт, вы соглашаетесь с использованием cookie в соответствии с Политикой обработки персональных данных.
```

Кнопка: «Принять».
Ссылка из текста: «Политикой обработки персональных данных» → /policy/.

## HTML-разметка

(Платформо-нейтральный пример. Для конкретной CMS — см. cms-fragments.md.)

```html
<div id="cookie-banner" class="cookie-banner" style="display:none">
  <p>...текст из блока выше...</p>
  <button type="button" id="cookie-accept">Принять</button>
</div>

<script>
  (function () {
    var key = 'cookieConsent';
    function get(n) { var m = document.cookie.match(new RegExp('(^|; )' + n + '=([^;]*)')); return m ? m[2] : null; }
    function set(n, v, d) { var t = new Date(); t.setTime(t.getTime() + d * 864e5); document.cookie = n + '=' + v + '; expires=' + t.toUTCString() + '; path=/; SameSite=Lax'; }
    if (!get(key)) {
      var el = document.getElementById('cookie-banner'); el.style.display = 'block';
      document.getElementById('cookie-accept').addEventListener('click', function () { set(key, 'Y', 365); el.style.display = 'none'; });
    }
  })();
</script>
```

CSS — компактный, fixed-bottom, не перекрывает важные элементы.

## CMS-специфика

(ВСТАВИТЬ из cms-fragments.md блок «Cookie» для {{CMS_NAME}})

## Поведение

- баннер показывается при первом визите (cookie `cookieConsent` отсутствует);
- по клику «Принять» — установить cookie на 1 год;
- повторно не показывать.

## QA

- [ ] баннер появляется в incognito;
- [ ] ссылка открывает /policy/;
- [ ] после «Принять» баннер скрывается и не возвращается;
- [ ] на mobile не перекрывает корзину/чат/важные кнопки.
