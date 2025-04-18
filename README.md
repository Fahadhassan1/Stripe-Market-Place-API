<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

# Laravel Stripe Connect Integration

This Laravel project includes integration with **Stripe Connect** to enable marketplace-style payments. The implementation includes a dedicated **StripeController** and a separate **StripeService** to manage all Stripe-related logic cleanly and efficiently.

---

## 🚀 Features

- Stripe Connect (Standard or Express) integration
- Account onboarding with OAuth flow
- Secure payouts to connected accounts
- Organized with Service-Controller pattern
- Clean `.env` config for sensitive Stripe keys

---

## 🛠 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Fahadhassan1/Stripe-Market-Place-API.git
cd Stripe-Market-Place

composer install

cp .env.example .env
php artisan key:generate

```
Update .env:

STRIPE_KEY=your_stripe_publishable_key
STRIPE_SECRET=your_stripe_secret_key
STRIPE_CLIENT_ID=your_stripe_connect_client_id
STRIPE_REDIRECT_URI=https://your-domain.com/stripe/callback

📁 File Structure

app/
├── Http/
│   └── Controllers/
│       └── StripeController.php
├── Services/
│   └── StripeService.php


🌐 Routes

Route::get('/stripe/connect', [StripeController::class, 'redirectToStripe']);
Route::get('/stripe/callback', [StripeController::class, 'handleStripeCallback']);


📌 Notes
Use HTTPS in production to avoid redirect/callback issues with Stripe.

Store your Stripe keys securely in the .env file.

Test using Stripe’s test keys before going live.


## License
Let me know if you want to include sample code for the controller or service directly in the readme, or keep them in their own files.

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
