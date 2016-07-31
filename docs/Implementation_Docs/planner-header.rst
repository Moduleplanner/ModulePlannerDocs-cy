.. _the-planner-header:

Pennawd y Cynllynydd
====================

Mae pennawd y cynllynydd yn cynnwys linciau llywio ac opsiynnau ar gyfer y cynllynydd modiwl, er engrhaifft iaith y wefan a'r botwm "Clirio dewisiadau".

.. highlight:: liquid

===========================
Dewis Cyfieithiadau Priodol
===========================

Mae angen i ni wneud yn siwr for y set o cyfieithiadau ar gyfer ein teitlau a'n pennawdau yn gywir, felly mae angen chwilio'r cronfa ddata ar gyfer y record cywir::

    {% for l in site.data.language %}
        {% if page.lang == l.short %}
            {% assign lang = l%}
        {% endif %}
    {% endfor %}

=================
Ysgrifennu'r HTML
=================

Rydym yn rhoi popeth o fewn elfen pennawd, ac y  dechrau wrth ysgrifennu'r linciau llywio::

    <header class="site-header">
        <div class="group">
            <a class="site-title" href="{{site.baseurl}}/{{lang.short}}/index.html">{{lang.change-deg}}</a>

Yna rydym yn ychwanegu menu dropdown sy'n cynnal holl themau'r wefan. Ar hyn o bryd ond :code:`Light` ac :code:`Dark` sydd. Ar gyfer mwy o wybodaeth gwelwch y tudalen :ref:`theme-changer`:

   <aside>
       <p>
           <span class="theme">
               {{lang.theme}}:
               <select id="theme-changer">
                   {% for theme in site.data.themes %}
                       <option value="{{theme.shortname}}">{{theme.name}}</option>
                   {% endfor %}
               </select>
           </span>

Yn dilyn proses debyg, mae angen menu dropdown ar gyfer y ieithoedd. Am fwy o wybodaeth gweler y tudalen :ref:`language-changer`::

    <span class="language">
        {{lang.language}}:
        <select id="lang-chooser">
            {% for langu in site.data.language %}
                <option value="{{langu.short}}">{{langu.name}}</option>
            {% endfor %}
        </select>
    </span>

Yna rydym yn cau'r elfennau :code:`p`, :code:`aside` a :code:`div` cyn ychwanegu botwm, "Clear Selected". Mae'r botwm yma mewn gwirionedd yn elfen pennawd, wedi'i steilio i edrych fel botwm::

    <div class="wrapper">
        <h1>{{course.name}}</h1>
        <h2 class="clear">{{lang.reset}}</h2>
    </div>


