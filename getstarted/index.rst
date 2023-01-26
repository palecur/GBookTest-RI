RIME overview
================================

.. include:: explanation/product-overview.md
   :parser: myst_parser.sphinx_

.. include:: explanation/summary_tests.md
   :parser: myst_parser.sphinx_

RI Platform consolidated test database
--------------------------------------
.. csv-table:: 
   :class: datatable
   :file: test_db.csv
   :widths: 4 4 4 28 22 22 14
   :header-rows: 1

All of the RIME tests are listed in the following sections, along with detailed descriptions.

Tabular
---------------------------------------
.. toctree::
   :maxdepth: 1

   explanation/tabular_test_categories.md
   explanation/tests/tabular/tests.md

NLP
---------------------------------------
.. toctree::
   :maxdepth: 1

   explanation/unstructured_test_categories.md
   explanation/tests/nlp/text_classification_tests.md
   explanation/tests/nlp/natural_language_inference_tests.md
   explanation/tests/nlp/named_entity_recognition_tests.md

CV
---------------------------------------
.. toctree::
   :maxdepth: 1

   explanation/unstructured_test_categories.md
   explanation/tests/cv/image_classification_tests.md
   explanation/tests/cv/object_detection_tests.md

RIME local trial
---------------------------------------
.. toctree::
   :maxdepth: 1

   local_trial/index.rst 
