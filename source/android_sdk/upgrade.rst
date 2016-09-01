.. _android_sdk/upgrade:
.. include:: /partials/common.rst

Upgrade
=======

Sometimes we need you to upgrade existing integration to use our latest features.

0.2.0
-----

Deep linking schema
...................

Add this to ``AndroidManifest.xml`` inside defenition of Talkable activity

.. code-block:: xml

  <intent-filter>
      <action android:name="android.intent.action.VIEW" />

      <category android:name="android.intent.category.DEFAULT" />
      <category android:name="android.intent.category.BROWSABLE" />

      <data android:scheme="tkbl-{{YOUR_SITE_SLUG}}" />
  </intent-filter>

Tracking app opening
....................

Replace ``Talkable.initialize(this);`` with ``Talkable.trackAppOpen(this);`` in your main activity.
Look in :ref:`installation section <main_activity_setup>` for more detailed information if needed.

0.1.0
-----

It's initial release, nothing to do.


.. container:: hidden

   .. toctree::
