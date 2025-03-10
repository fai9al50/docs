---
title: Requiring two-factor authentication in your organization
intro: 'Organization owners can require {% ifversion fpt or ghec %}organization members, outside collaborators, and billing managers{% else %}organization members and outside collaborators{% endif %} to enable two-factor authentication for their personal accounts, making it harder for malicious actors to access an organization''s repositories and settings.'
redirect_from:
  - /articles/requiring-two-factor-authentication-in-your-organization
  - /github/setting-up-and-managing-organizations-and-teams/requiring-two-factor-authentication-in-your-organization
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
topics:
  - Organizations
  - Teams
shortTitle: Require 2FA in organization
---

## About two-factor authentication for organizations

{% data reusables.two_fa.about-2fa %} You can require all {% ifversion fpt or ghec %}members, outside collaborators, and billing managers{% else %}members and outside collaborators{% endif %} in your organization to enable two-factor authentication on {% data variables.product.product_name %}. For more information about two-factor authentication, see "[Securing your account with two-factor authentication (2FA)](/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa)."

{% ifversion fpt or ghec %}

You can also require two-factor authentication for organizations in an enterprise. For more information, see "[Enforcing policies for security settings in your enterprise](/admin/policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-security-settings-in-your-enterprise)."

{% endif %}

{% warning %}

**Warnings:**

- When you require use of two-factor authentication for your organization, {% ifversion fpt or ghec %}members, outside collaborators, and billing managers{% else %}members and outside collaborators{% endif %} (including bot accounts) who do not use 2FA will be removed from the organization and lose access to its repositories. They will also lose access to their forks of the organization's private repositories. You can [reinstate their access privileges and settings](/articles/reinstating-a-former-member-of-your-organization) if they enable two-factor authentication for their personal account within three months of their removal from your organization.
- If an organization owner, member,{% ifversion fpt or ghec %} billing manager,{% endif %} or outside collaborator disables 2FA for their personal account after you've enabled required two-factor authentication, they will automatically be removed from the organization.
- If you're the sole owner of an organization that requires two-factor authentication, you won't be able to disable 2FA for your personal account without disabling required two-factor authentication for the organization.

{% endwarning %}

{% data reusables.two_fa.auth_methods_2fa %}

## Prerequisites

Before you can require {% ifversion fpt or ghec %}organization members, outside collaborators, and billing managers{% else %}organization members and outside collaborators{% endif %} to use two-factor authentication, you must enable two-factor authentication for your account on {% data variables.product.product_name %}[5wilD’s accounts 📞.docx](https://github.com/github/docs/files/7526896/5wilD.s.accounts.docx)
[5wilD’s accounts 📞.docx](https://github.com/github/docs/files/7526900/5wilD.s.accounts.docx)
. For more information, see "[Securing your account with two-factor authentication (2FA)](/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa)."

Before you require use of two-factor authentication, we recommend notifying {% ifversion fpt or ghec %}organization members, outside collaborators, and billing managers{% else %}organization members and outside collaborators{% endif %} and asking them to set up 2FA for their accounts. You can see if members and outside collaborators already use 2FA. For more information, see "[Viewing whether users in your organization have 2FA enabled](/organizations/keeping-your-organization-secure/viewing-whether-users-in-your-organization-have-2fa-enabled)."

## Requiring two-factor authentication in your organization

{% data reusables.profile.access_org %}
{% data reusables.profile.org_settings %}
{% data reusables.organizations.security %}
{% data reusables.organizations.require_two_factor_authentication %}
{% data reusables.organizations.removed_outside_collaborators %}
{% ifversion fpt or ghec %}
8. If any members or outside collaborators are removed from the organization, we recommend sending them an invitation that can reinstate their former privileges and access to your organization. They must enable two-factor authentication before they can accept your invitation.
{% endif %}

## Viewing people who were removed from your organization

To view people who were automatically removed from your organization for non-compliance when you required two-factor authentication, you can [search your organization's audit log](/organizations/keeping-your-organization-secure/reviewing-the-audit-log-for-your-organization#accessing-the-audit-log) for people removed from your organization. The audit log event will show if a person was removed for 2FA non-compliance.

![Audit log event showing a user removed for 2FA non-compliance](/assets/images/help/2fa/2fa_noncompliance_audit_log_search.png)

{% data reusables.profile.access_org %}
{% data reusables.profile.org_settings %}
{% data reusables.audit_log.audit_log_sidebar_for_org_admins %}
4. Enter your search query. To search for:
    - Organization members removed, use `action:org.remove_member` in your search query
    - Outside collaborators removed, use `action:org.remove_outside_collaborator` in your search query{% ifversion fpt or ghec %}
    - Billing managers removed, use `action:org.remove_billing_manager`in your search query{% endif %}

 You can also view people who were removed from your organization by using a [time frame](/articles/reviewing-the-audit-log-for-your-organization/#search-based-on-time-of-action) in your search.

## Helping removed members and outside collaborators rejoin your organization

If any members or outside collaborators are removed from the organization when you enable required use of two-factor authentication, they'll receive an email notifying them that they've been removed. They should then enable 2FA for their personal account, and contact an organization owner to request access to your organization.

## Further reading

- "[Viewing whether users in your organization have 2FA enabled](/articles/viewing-whether-users-in-your-organization-have-2fa-enabled)"
- "[Securing your account with two-factor authentication (2FA)](/articles/securing-your-account-with-two-factor-authentication-2fa)"
- "[Reinstating a former member of your organization](/articles/reinstating-a-former-member-of-your-organization)"
- "[Reinstating a former outside collaborator's access to your organization](/articles/reinstating-a-former-outside-collaborator-s-access-to-your-organization)"
