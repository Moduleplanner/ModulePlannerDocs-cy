.. _language:

=========
Ieithoedd
=========

Yr iaith diofyn ar gyfer y Cynllunydd Modiwlau yw Saesneg, ond mae hefyd yr opsiwn i'w weld yn Gymraeg. I ychwanegu iaith arall i'r cronfa ddata mae angen mewnbynnu'r data o fewn i'r ffeil :code:`language.yml' yn y ffolder :code:`_data'. Cyn ychwanegu iaith newydd, mae angen cyfeithiadau'r geiriau/brawddegau yma:

* Blwyddyn
* yma
* Thema
* Credydau
* Iaith
* modiwlau ofynnol
* Mwy o wybodaeth
* Clirio dewisiadau
* Credydau a ddewiswyd
* Dewiswch eich cynllun gradd os gwelwch yn dda
* Newidwch eich cynllun gradd
* Gan fod hwn yn cael ei chynnal gan fyfyrwyr, efallai na fydd y wybodaeth yn gwbl gywir.
* Ond y modiwlau safonol y gallwch eu cymryd yn ystod eich gradd sydd fan hyn, cliciwch i weld yr holl fodiwlau posib ar gyfer eich gradd.
* Gan fod hwn wedi'i cynnal gan myfyrwyr, efallai nad yw'r holl wybodaeth yn gywir.

Mae hefyd angen cod rhyngwladol yr iaith (gweler`Language-codes
<http://www.sitepoint.com/web-foundations/iso-2-letter-language-codes/>`_
am gymorth) a cyfieithiad enw'r ysgol.


Engrhaifft: Ychwanegu Sbaeneg
=============================

Cod rhyngwladol ar gyfer Sbaeneg yw :code:`es` ac enw fy ysgol yw: :code:`Yr Ysgol Mathemateg`, sy'n cyfeithu yn Sbaeng fel: :code:`Escuela de Matemáticas`. Cyfieithiadau'r geiriad/brawddegau uchod yw:

* Año
* aquí
* Tema
* Claro Seleccionada
* Crédito
* Idioma
* Requiere
* Más información
* Por favor elija su grado
* Cambiar su esquema de grado
* Créditos elegidos
* Esto es sólo los módulos estándar que puede tomar durante su grado, para ver todos los posibles módulos para obtener su título por favor haga clic
* Como esto se maintainted por los estudiantes, la infomación puede no ser del todo correcta.

Yr hyn sydd angen ysgrifennu yn language.yml yw::

	- name: Es
	  year: Año
	  here: aquí
	  theme: Tema
	  reset: Claro Seleccionada
	  credits: Crédito
	  language: Idioma
	  requires: Requiere
	  more-info: Más información
	  select-deg: Por favor elija su grado
	  change-deg: Cambiar su esquema de grado
	  school-name: Escuela de Matemáticas
	  language-code: es
	  credits-chosen: Créditos elegidos
	  more-options: Esto es sólo los módulos estándar que puede tomar durante su grado, para ver todos los posibles módulos para obtener su título por favor haga clic
	  disclaimer: Como esto se maintainted por los estudiantes, la infomación puede no ser del todo correcta.

Ac yna creu ffolder yn y ffolder sylfaenol wedi'i enwi :code:`es` lle byddwch yn rhoi'r fersiwn Sbaeneg o'r ffeiliau html y graddau.
