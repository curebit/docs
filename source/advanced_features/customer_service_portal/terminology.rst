.. _advanced_features/customer_service_portal/terminology:
.. include:: /partials/common.rst

Terminology
===========

Referral
--------

This is a connection between an |advocate| and a |friend| who completed a referral purchase from the
Advocate’s invite (a share). A referral will not be created unless the following 3 pieces are known: Advocate Email,
Friend Email, and a Purchase made by a Referred Friend. Each referral is passed through several fraud checks
(configured inside Fraud Settings). As a result of the fraud checks each referral status can be:

 1. **In progress**: Talkable referral engine is processing the referral. Such action usually takes less than a second
    so it is highly unlikely that you will see this status. No rewards are issued at this point.

 2. **Pending**: a referral is pending approval. Talkable referral engine can either approve referrals automatically
    with some delay (optionally) or leave this decision to the user (manual, not recommended as it leads to
    backlogged referrals). Thus, if the referral fraud checks were passed successfully each referral stays in Pending
    status until they are approved automatically based on the auto-approval delay configuration (configured inside Fraud
    Settings). No rewards are issued at this point.

 3. **Flagged**: due to having many different options to configure referral fraud checks, it is not always possible to
    set up an automatic resolution for each referral. For such cases, you may want to Flag referrals that are in a so
    called grey area, where the chance of fraud is around 50% and it is impossible to make the decision automatically.
    All flagged referrals are added to a queue for manual resolution and can be accessed inside CSP → Referrals.
    No rewards are issued at this point.

 4. **Approved**: this is a valid referral status which either gets set by the Talkable referral engine with automatic
    approval or by a user in case of manual resolution. Flagged referrals can also turn to approved since they are
    resolved manually. All rewards associated with the referral are then passed to the next stage to verify if they
    can be issued.

 5. **Voided**: this status is set by a user manually if they decide a referral is invalid and there should be no
    rewards issued as a result. Only pending and flagged referrals can be voided. Talkable referral engine cannot set
    this status automatically. All rewards associated with the referral are getting blocked as a result.

 6. **Blocked**: when some fraud checks are failed Talkable referral engine blocks the referral immediately. All rewards
    associated with the referral are getting blocked as a result.

Reward
------

This is what the person gets as a result of some action (incentive). Available reward statuses:

- **Pending**: the reward is awaiting referral approval. The referral can either be approved manually or automatically,
  depending on your configuration.

- **Waiting for coupon**: there are not enough coupons left to pay the reward. The reward will remain in a 'waiting'
  status until more coupons are uploaded into the associated coupon list.

- **Given**: the reward was paid to the person but Talkable does not have information as to whether it was used or not.
  Most likely it was not yet used.

- **Voided**: the reward was voided because the referral was voided by a user manually.

- **Blocked/No reward**: there was no reward created either because the associated referral was blocked according to
  Fraud Settings or because of other reasons: incentive criteria has blocked it, or the person was blacklisted.

.. container:: hidden

   .. toctree::