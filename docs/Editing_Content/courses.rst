.. _courses:

================
Cynlluniau Gradd
================

Felly rydych wedi ychwanegu'r holl modiwlau i mewn i'r system (gweler :ref:`modules` i weld sut i gwneud hwn) nawr rhaid ychwanegu cymlluniau gradd i'r cronfa ddata. Mae gwybodaeth cynlluniau gradd wedi'i cadw yn y ffeil :code:`courses.yml` yn y ffolder :code:`_data`. Y wybodaeth sydd angen yw:

* Codau cenedlaethol y cynllyn gradd (y cod UCAS yn yr DU)
* Enw'r gradd
* Codau modiwl ar gyfer y modiwlau craidd ac opsiynnol ar gyfer y blwyddyn 1 :sup:`af`
* Codau modiwl ar gyfer y modiwlau craidd ac opsiynnol ar gyfer yr 2 :cup:`ail` blwyddyn
* ayyb... (parhewch ar gyfer pob blwyddyn y gradd)

Gradd Engrheifftiol
===================

Enw'r gradd byddaf yn ychwanegu yw BSc Mathematics, gyda'r enw byr bsc. Mae'n gradd tri blwyddyn, ac yn cynnwys y codau modiwl canlynnol:


* Blwyddyn 1 :sup:`af` craidd: ma1001, ma1004, ma1005, ma1007, ma1500, ma1006, ma1003
* Blwyddyn 1 :sup:`af` opsiynnol: ma0111, ma1300, ma1501
* 2 :sup:`ail` blwyddyn craidd: ma0221, ma0212, ma2004, ma2001, ma2002, ma2003
* 2 :sup:`ail`bwyddyn opsiynnol: ma0235, ma2005, ma2500, cm2203, ma2501, ma0213,	cm2207
* 3 :sup:`ydd` blwyddyn opsiynnol: ma0332, ma3505, ma3504, ma3602, ma3601, ma3901, cm3201, cm3111

Yn courses.yml ysgrifennwch::

	- degree-code: G100
	  name: BSc Mathematics
	  modules:
		  - core: ['ma1001', 'ma1004', 'ma1005', 'ma1007', 'ma1500', 'ma1006', 'ma1003']
			optional: ['ma0111', 'ma1300', 'ma1501']

		  - core: ['ma0221', 'ma0212', 'ma2004', 'ma2001', 'ma2002', 'ma2003']
			optional: ['ma0235', 'ma2005', 'ma2500', 'cm2203', 'ma2501', 'ma0213',	'cm2207']

		  - optional: ['ma0332', 'ma3505', 'ma3504', 'ma3602', 'ma3601', 'ma3901', 'cm3201', 'cm3111']


Nawr rydym wedi ychwanegu BSc Mathematics i'r cronfa ddata, mae angen i ni creu'r ffeil html iddo. Mae hwn yn byw yn y ffolder iaith. (Yn yr ystorfa gwreiddiol mae dau iaith - Cymraeg a Saesneg, felly mae ganddyn ni dau ffolder :code:`cy` a :code:`en` i dal y ffeiliau html).

Yn y ffeilm bsc.html rhaid ysgrifennu::

	---
	layout: course
	degree-code: G100
	lang: en
	---

Ar gyfer y ffeil G100.html yn y ffolder cy, yr unig wahaniaeth yw :code:`lang: cy' yn lle.
