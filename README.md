# BUILD X

A static website for electronics and robotics project guides, code, software links, a simulator and a materials shop. The site is published with GitHub Pages.

## Publish the website

1. Upload `index.html`, the `assets` folder and `.nojekyll` to the root of your GitHub repository.
2. In GitHub, open **Settings → Pages**.
3. Choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Your site will appear at your GitHub Pages address after the build completes.

## Save admin edits permanently

Admin edits are saved locally in the browser so they can be restored when you sign in again on that browser. To make edits available to every visitor and across devices, you must publish them:

1. In GitHub, open **Settings → Developer settings → Personal access tokens → Fine-grained tokens**.
2. Create a token restricted to this repository and grant **Contents: Read and write**.
3. On the live BUILD X site, sign in to **Admin**.
4. Under **Publish to everyone**, enter the GitHub owner, repository, branch (`main`) and token, then select **Publish changes**.
5. Reload the public site after GitHub Pages has deployed the changes.

Keep the GitHub token private. It is entered into the admin publishing form and held only for the current tab session.

## Founder and Co-Founder profiles

The Admin page has separate edit controls for Founder and Co-Founder. Both profiles are included in `content.json` when published. The Founder retains the video controls; the Co-Founder page intentionally has no video section.

## EmailJS setup

The Admin page contains separate fields for the visitor welcome template and the order-notification template.

1. Create an EmailJS account and connect the email service you want to send from.
2. Copy your EmailJS **Public Key** and **Service ID**.
3. Create a welcome template. Set its recipient field to `{{to_email}}`, then copy its Template ID into **Welcome template ID**.
4. Create a second template for purchase-intent notifications. Set its recipient field to `{{to_email}}` and copy its Template ID into **Order notification template ID**.
5. The order notification is addressed to `samaryan.p@gmail.com` and includes these template variables: `{{order_reference}}`, `{{customer_name}}`, `{{customer_email}}`, `{{customer_address}}`, `{{order_items}}`, `{{subtotal}}`, `{{shipping}}`, `{{order_total}}`, `{{currency}}`, `{{payment_status}}`, `{{site_name}}` and `{{site_url}}`.
6. Enter the Public Key, Service ID and both template IDs in Admin, save, then **Publish changes**.
7. In EmailJS account security settings, restrict allowed origins to your website domain.

The order email is a **pre-payment purchase-intent alert**. It does not mean the customer has paid or that an order is confirmed. This project currently has no payment provider connected, and the site does not collect or process card details. Add a secure backend and a supported payment provider before accepting real payments. A client-side EmailJS notification is suitable for a prototype, but it is not a tamper-proof order system.

## Logo

The BUILD X logo and favicon are in `assets/`. Keep that folder alongside `index.html` when uploading the site.

## Important before launch

Review the sample product prices, stock, shipping terms, returns policy and contact information. Replace all sample content with accurate business information before opening the shop to customers.
