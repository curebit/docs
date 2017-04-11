.. _android_sdk/advanced:
.. include:: /partials/common.rst

Advanced Usage
==============

Overriding default behaviour
----------------------------

1. Create a new fragment in your app which extends `TalkableOfferFragment`
   and override methods there. Example:

  .. code-block:: java

    import com.talkable.sdk.TalkableOfferFragment;

    public class OverriddenTalkableOfferFragment extends TalkableOfferFragment {
        @Override
        public void copyToClipboard(String string) {
            super.copyToClipboard(string);

            Toast.makeText(getActivity(), "Text copied!", Toast.LENGTH_LONG).show();
        }
    }


2. Pass an activity you want to run a fragment in and the overriden fragment classes to
   `Talkable.showOffer` call:

  .. code-block:: java

    Talkable.showOffer(activity, affiliateMember, MyFragmentActivity.class, OverridenTalkableOfferFragment.class);

And change the manifest:

  .. code-block:: xml

    <!-- From -->
    <activity android:name="com.talkable.sdk.TalkableActivity" />

    <!-- To -->
    <activity android:name=".MyFragmentActivity" />

.. note::
   You can just override TalkableOfferFragment and use default TalkableActivity from Talkable SDK.
   In this case you shouldn't change the manifest
   (if you did steps from :ref:`Getting Started <android_sdk/getting_started>` section).

  .. code-block:: java

    Talkable.showOffer(activity, affiliateMember, TalkableActivity.class, OverridenTalkableOfferFragment.class);

Using TalkableOfferFragment directly
------------------------------------

At first you should :ref:`create an origin <android_sdk/integration>`.
Then you should pass it to TalkableOfferFragment via Bundle.
After this you can start using the fragment.

.. code-block:: java

  AffiliateMember affiliateMember = new AffiliateMember();

  Bundle arguments = new Bundle();
  arguments.putParcelable(TalkableOfferFragment.ORIGIN_PARAM, affiliateMember);

  TalkableOfferFragment talkableOfferFragment = new TalkableOfferFragment();
  talkableOfferFragment.setArguments(arguments);

.. container:: hidden

   .. toctree::
