.. _theme-changer:

Newidiwr Thema
==============

Mae'r tudalen yma yn dangos sut mae'r newidiwr thema yn gweithredu. Ar y tudalen :ref:`the-planner-header` eithon ni twy sut ychwanegon ni dewislen dropdown i'r pennawd ar y tudalen sy'n cynnwys holl themau sydd wedi'i osod ar y wefan ar hyn o bryd. Fan hyn rydym yn mynd trwy'r Javascript sydd angen i gwneud dewisiad ac gymhwyso'r thema yna.


.. highlight:: html

Mae "themau" wedi'i creu gan stylesheets CSS ac wedi'i llwytho yn y rhan :code:`<head>` y dudalen HTML::

    <link rel="stylesheet" href="/path/to/file.css">

Mae newid y priodoledd :code:`href` yn galluogu'r porwr derbyn a gymhwyso'r stylesheet newydd, ac felly "thema" newydd.

=======
Y Setup
=======

.. highlight:: javascript

Gadewch i ni cerdded trwy y cod sy'n cael ei rhedeg wrth i'r tudalen llwytho. Yn gyntaf diffiniwn rhai newidynnau::

    var stylesheet = "link#theme-def";
    var themechooser = "select#theme-chooser";

Yna rydym yn gweld os yw'r defnyddiwr wedi safio ynrhyw ffafriaeth blaenorol, ac yna gymhwyso'r thema yna neu'r thema diofyn::

    if (localStorage.theme) {

        changeTheme(localStorage.theme);
    } else {

        changeTheme("dark");
    }

Yna rhaid dweud wrth y dewislen dropdown i newid y thema pan mae defnyddiwr yn dewis thema newydd::

    $(themechooser).chnage(function () {

        var new_theme = $(themechooser).val();
        changeTheme(new_theme);
    });

Ond angen ysgrifennu'r ffwthiant :code:`changeTheme` sydd ar ol.

========================
Y Ffwythiant Newid Thema
========================

Mae angen ffwythiant sy'n cymryd i fewn enw ffeil ar gyfer thema (heb yr estyniad), ac sy'n gwneud i'r porwr llwytho a gymhwyso'r thema yna. Diolch i jQuery mae hwn yn hawdd::

    var changeTheme = function(shortname) {
  
        $(stylesheet).attr("href", "/css/" + shortname + ".css");

Nesa gwnewch yn siwr fod y dewislen dropdown yn cyfateb a'r thema newydd::

    $(themechooser).val(shortname);

Yn olaf rhaid safio'r dewis hwn yn y storfa lleol os oes yna storfa lleol::

    if (typeof(Storage)) {
        localStorage.setItem("theme", shortname);
    }
