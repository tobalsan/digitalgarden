---
{"created":"2024-12-21T17:08","type":"article","project":[["noobthink.com"]],"dg-publish":true,"tags":["article"],"permalink":"/notes/how-to-fix-google-o-auth-credentials-expiring-after-7-days-in-n8n/","dgPassFrontmatter":true,"updated":"2025-04-18T14:35:16.386+02:00"}
---

# How to Fix Google OAuth Credentials Expiring After 7 Days in n8n

If you're using a self-hosted **n8n** instance and encountering issues with Google OAuth credentials expiring every 7 days due to your app not being validated by Google, here's a straightforward fix. By adjusting the consent screen settings, you can bypass Google's extended validation process and make your app production-ready.

---

## Steps to Fix the Issue:

1. **Access Google Cloud Console:**
   - Log in to your Google Cloud Console.
   - Navigate to the project associated with your n8n workflows.

2. **Go to the OAuth Consent Screen:**
   - In the left-hand menu, go to **APIs & Services > OAuth Consent Screen**.

3. **Remove the Logo:**
   - If you've uploaded a logo for your app, remove it from the consent screen settings. The logo triggers additional validation requirements that prolong the process.

4. **Publish the App:**
   - Scroll down to the bottom of the consent screen page and click **Publish App** to move your app from **Testing** to **Production**.

5. **Confirm the Changes:**
   - Ensure that your app status is now listed as **In Production**. This prevents your OAuth tokens from expiring after 7 days.

6. **Test the Integration:**
   - Go back to your n8n workflows and ensure that Google services are properly integrated and the credentials remain active beyond the 7-day limit.

---

By removing the logo and publishing your app, you can avoid the cumbersome app verification process while ensuring that your Google OAuth credentials remain valid for longer durations.