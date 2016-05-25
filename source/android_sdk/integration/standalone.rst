.. _android_sdk/integration/standalone:
.. include:: /partials/common.rst

Standalone Campaign
===================

Let’s take a look at how the Standalone campaign integration looks. The main purpose
of this type of campaign is to drive your users to invite their friends (to become Advocates)
without being gated by a purchase beforehand.

Usually Standalone campaign look like a separate widget that people can access by clicking on
the “Invite friends” button inside app navigation.

Once you’ve got a Standalone campaign set up inside Talkable you can integrate the campaign
with the following line of code:

.. code-block:: java

  import com.talkable.sdk.Talkable;
  ...

  Activity activity = this;
  String campaignTag = "invite";
  Talkable.showOffer(activity, campaignTag);
  ...
  
.. note::
  
  Make sure you have at least one live “SA” campaign with a specified tag inside Talkable Site
  
Note that `customer` is empty, in this case user will see the
:ref:`Advocate Signup Page <campaigns/views/affiliate_members_new>`, which is used to collect
the user’s email address. Your application may already know/have access to the user’s email,
if so, you should pass this parameter which will automatically skip the SignUp Page in the
flow and show the :ref:`Advocate Share Page <campaigns/views/offers_show>`.

.. code-block:: java
  
  import com.talkable.*;
  ...

  String email = "advocate@example.com"; // Required
  String idInYourApp = "a8db7683-0f7f-407e-8d12-af2d501035c8"; // Use unique identifier from your system, optional
  String firstName = "John"; // Optional
  String lastName = "Smith"; // Optional

  Activity activity = this;
  String campaignTag = "invite";
  Customer customer = new Customer(idInYourApp, firstName, lastName, email);
  Talkable.showOffer(activity, campaignTag, customer);
  ...

.. container:: hidden

   .. toctree::
