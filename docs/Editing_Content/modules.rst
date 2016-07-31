.. _modules:

========
Modiwlau
========
Er mwyn ychwanegu modiwl i'r cronfa ddata, rhaid mewnbynnu data i fewn i'r ffeil :code:`modules.yml` yn y ffolder :code:`_data`. Cyn gwneud hwn, gwnewch yn siwr fod y wybodaeth canlynol ganddoch:

* Cod y modiwl
* Enw'r modiwl
* Gwerth credydau'r modiwl
* Cod y modiwlau sydd angen eu gymryd cyn cymryd y modiwl yma

Os nad oes unrhyw rhagofynion gyda'r modiwl rydych yn trio ychwanegu, paid poenu, dyma dau engrhaifft o ychwanegu modiwl newydd: un gyda rhagofynion ac un heb rhagofynion.

Engrhaifft 1: gyda rhagofynion
==============================

Enw'r modiwl byddaf yn ychwanegu yw :code:`Elementary Fluid Dynamics`. Mae hwn werth :code:`10 credyd` gyda'r code :code:`ma0235`. Er mwyn cymryd y modiwl rhaid i'r myfyriwr cymryd modiwlau Mechanics 1 a Vector Calculus sydd a'r codau modiwl :code:`ma1300` a :code:`ma2301` yn y trefn yna.

Dyma beth sydd rhaid ysgrifennu yn modules.yml::

	- code: ma0235
	  name: Elementary Fluid Dynamics
	  credits: 10
	  requires: ['ma1300', 'ma2301']

Engrhaifft 2: heb rhagofynion
=============================

Enw'r modiwl byddaf yn ychwanegu yw :code:`MOdelling with Differential Equations`. Mae hwn werth :code:`10 credyd` gyda'r code :code:`ma0232`.

The module I am going to add is called :code:`Modelling with Differential
Equations`.  This is a :code:`10 credit` module with the module code:
:code:`ma0232`.

Dyma beth sydd rhaid ysgrifennu yn modules.yml::

	- code: ma0232
	  name: Modelling with Differential Equations
	  credits: 10

Rydych nawr yn gwbod sut i ychwanegu modiwlau i'r cronfa ddata. Unwaith rydych wedi ychwanegu'r holl modiwlau rydych yn barod i ychwanegu :ref:`courses` eich ysgol.
