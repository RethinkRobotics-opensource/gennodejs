^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package gennodejs
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1.0.3 (2016-5-18)
------------------
* Removed extraneous base file installs
* Revert install space fix that re-used base js files per package
* Added install space fix that copies base js files per package
* Contributors: Ian McMahon, Rob Linsalata

1.0.2 (2016-5-18)
------------------
* Fixed gennodejs file deployment in install space
* Fixed a python3 incompatibility in generate.py
* Contributors: Chris Smith, Ian McMahon, Maarten de Vries

1.0.1 (2016-4-27)
-----------
* Package name-switch from genjs to gennodejs based on feedback
* When deserializing, creates an instance of the message
  rather than using json.
* Update genjs for install
  -No longer includes hardcoded paths in generated message files
  -Actually install stuff
* Contributors: Chris Smith, Ian McMahon, chris-smith

1.0.0 (2016-4-19)
------------------
* Initial Release
* ROS JS Message Generation
* Builds automatically with catkin
* Include support for ROS Services
* Constants, Msg instances
  -generated msgs are now classes
  -msgs have constants included
* Contributors: Chris Smith, Ian McMahon
