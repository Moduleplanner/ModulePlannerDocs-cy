.. _course-page:

Y Dudalen Gradd
===============

.. highlight:: yaml

I ailadrodd yr hyn sydd yn y dudalen :ref:`courses` y ffordd i gael Jekyll i generadu tudalen o cynllun graff yw i cael y defnyddiwr i greu ffail a datparu tri darn o wybodaeth::

     ---
     layout: course
     short: <degree-scheme>
     lang: <language-code>
     ---

Mae hwn yn golygu allwn ni cymryd y tri darn o wybodaeth yma yn unig a creu popeth sydd angen, nid yn unig wybodaeth i ymwelwyr y wefan, ond hefyd digon o strwythur i'r Javascript trafod :ref:`module-selection`.

.. highlight:: liquid

=======================
Derbyn Manylion y Gradd
=======================

Ond darn o cod byr sydd ganddyn yn cynrychiolu'r cynllun gradd, mae angen i ni cael y record llawn o'r cronfa ddata. Gan fod y cod yma un unigryw, yn syml fe allen ni mynd trwy pob record nes ein bod wedi cyrraedd yr un cywir::

    {% for c in site.data.courses %}
        {% if c.short == page.short %}
            {% assign course = c %}        
        {% endif %}
    {% endfor %}

Fe allwch ffeindio mwy o wybodaeth ar strwythyr y gwrthrych cwrs ar y tudalen :ref:`courses`.


===========================
Dewis Cyfieithiadau Priodol
===========================

Mae angen i ni dewid y cyfieithiadau cywir ar gyfer ein teitlau a'n penawdau, felly yn debyg i'r hyn a wnaethon ni uchod rhaid chwilio trwy'r holl cronfa ddata ar gyfer y record cywir::

    {% for l in site.data.language %}
        {% if page.lang == l.short %}
            {% assign lang = l%}
        {% endif %}
    {% endfor %}


=================
Ysgrifennu'r HTML
=================
Nawr bod ganddyn yr holl wybodaeth angenrheidiol gallwn dechrau ysgrifennu HTML y wefan. Dechreuwn gan cynnwyd y :ref:`the-planner-header` sy'n cynnwys y bottwm clirio, ac opsiynnau fel thema ac iaith::

    {% include planner_header.html %}

Nawr rydym yn ymlapio popeth mewn elfen :code:`code` gyda'r dosbarth :code:`planner` felly allwn ffeidio popeth gyda'r Javascript nes mlaen. Dechreuwn pob blwyddyn gan ysgrifennu ei enw ac ychwanegu rhifydd sy'n cadw trac o'r nifer o gredydau mae'r defnyddiwr wedi dewis::

    <div class="planner">

    {% for year in course.modules %}
        <div class="year" id="year{{forloop.index}}">
             <h1>{{lang.year}} {{forloop.index}}</h1>
             <h3>{{lang.credits-chosen}}: <span class="credit"></span></h3>

Noder ni pennwn gwerth cychwynnol ar gyfer y nifer o gredydau a ddewisiwyd, mae hwn yn cael ei pennu yn y Javascript gan fod y gwerth cychwynnol yn dibynnu ar nifer o modiwlau craidd y cynllun gradd yna yn y blwyddyn yna.

Yna rydym yn rhestru pob modiwl craidd::

    <div class="core">
    {% for code in year.core %}

        <div class="module selected" id="{{code}}">
            {% include module_info.html %}
        </div>
    {% endfor %}
    </div>

Mae'r HTML ar gyfer gwybodaeth modiwl a'r lunwedd yn cael ei trafod gan y templed :code:`_includes/module_info.html`, gallwch ffeindio mwy o wybodaeth ar y tudalen :ref:`module-html`. Gan fod y modiwlau craidd yn ofynnol, ychwanegwn y dosbarth :code:`selected` i'r :code:`div` sy'n ymlapio pob modiwl, felly mae'r Javascript yn gwbod pa modiwlau a ddewiswyd.

Nesaf rhestrwn y modiwlau opsiynnol ar gyfer y blwyddyn::

      <div class="optional">
      {% for code in year.optional %}

          <div class="module" id="{{code}}">
              {% include module_info.html %}
          </div>
      {% endfor %}
      </div>
    
Yr unig peth sydd ar ol i'w wneud yw cau'r elfennau :code:`div` sy'n weddill a'r prif loop (sydd wedi hepgor o'r tudalen yma). Gallwch ffeindio'r holl cod uchod yn y ffeil :code:`_layouts/course.html`.
