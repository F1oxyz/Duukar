# Duukar Flutter Architecture Tree

Base propuesta para `lib/` usando enfoque **feature-first** simple, escalable y rápido para hackathon.

## Árbol real de carpetas

```text
lib/
├── app/
│   ├── app.dart
│   ├── router/
│   │   └── app_router.dart
│   └── theme/
│       ├── app_colors.dart
│       ├── app_text_styles.dart
│       └── app_theme.dart
├── core/
│   ├── constants/
│   │   └── app_constants.dart
│   ├── utils/
│   │   ├── result.dart
│   │   └── validators.dart
│   └── widgets/
│       ├── app_scaffold.dart
│       ├── app_text_field.dart
│       ├── loading_view.dart
│       └── primary_button.dart
├── features/
│   ├── analysis/
│   │   ├── data/
│   │   │   └── analysis_repository.dart
│   │   ├── domain/
│   │   │   ├── analysis_request.dart
│   │   │   └── analysis_result.dart
│   │   ├── presentation/
│   │   │   ├── analysis_history_screen.dart
│   │   │   ├── analysis_result_screen.dart
│   │   │   ├── analysis_type_screen.dart
│   │   │   ├── analyzing_screen.dart
│   │   │   ├── ask_duki_screen.dart
│   │   │   ├── extended_explanation_screen.dart
│   │   │   ├── paste_link_screen.dart
│   │   │   ├── paste_text_screen.dart
│   │   │   ├── recommendation_screen.dart
│   │   │   └── upload_capture_screen.dart
│   │   └── providers/
│   │       └── analysis_provider.dart
│   ├── auth/
│   │   ├── data/
│   │   │   └── auth_repository.dart
│   │   ├── presentation/
│   │   │   ├── forgot_password_screen.dart
│   │   │   ├── login_screen.dart
│   │   │   ├── register_screen.dart
│   │   │   └── verify_account_screen.dart
│   │   └── providers/
│   │       └── auth_provider.dart
│   ├── home/
│   │   └── presentation/
│   │       ├── home_kids_screen.dart
│   │       └── home_teens_screen.dart
│   ├── lessons/
│   │   ├── data/
│   │   │   └── lessons_repository.dart
│   │   ├── domain/
│   │   │   └── lesson.dart
│   │   ├── presentation/
│   │   │   ├── lesson_detail_screen.dart
│   │   │   ├── lesson_library_screen.dart
│   │   │   ├── mandatory_lesson_1_screen.dart
│   │   │   ├── mandatory_lesson_2_screen.dart
│   │   │   ├── mandatory_lesson_3_screen.dart
│   │   │   └── reward_screen.dart
│   │   └── providers/
│   │       └── lessons_provider.dart
│   ├── onboarding/
│   │   └── presentation/
│   │       ├── intro_duki_screen.dart
│   │       ├── navigation_tutorial_screen.dart
│   │       ├── splash_screen.dart
│   │       └── welcome_screen.dart
│   ├── reports/
│   │   ├── data/
│   │   │   └── reports_repository.dart
│   │   ├── presentation/
│   │   │   ├── confirm_report_screen.dart
│   │   │   ├── report_form_screen.dart
│   │   │   ├── report_platform_tutorial_screen.dart
│   │   │   ├── report_sent_screen.dart
│   │   │   └── reports_history_screen.dart
│   │   └── providers/
│   │       └── reports_provider.dart
│   ├── rewards/
│   │   └── presentation/
│   │       ├── achievements_screen.dart
│   │       ├── progress_profile_screen.dart
│   │       └── shop_screen.dart
│   └── settings/
│       └── presentation/
│           ├── account_deleted_screen.dart
│           ├── delete_account_screen.dart
│           ├── help_support_screen.dart
│           ├── logout_screen.dart
│           ├── manage_data_screen.dart
│           ├── privacy_policy_screen.dart
│           ├── privacy_screen.dart
│           ├── profile_screen.dart
│           ├── settings_screen.dart
│           └── terms_screen.dart
└── main.dart
```

## Comando para crear todo desde consola

Ejecutar desde la raíz del proyecto Flutter:

```bash
mkdir -p lib/app/router lib/app/theme lib/core/constants lib/core/utils lib/core/widgets lib/features/analysis/data lib/features/analysis/domain lib/features/analysis/presentation lib/features/analysis/providers lib/features/auth/data lib/features/auth/presentation lib/features/auth/providers lib/features/home/presentation lib/features/lessons/data lib/features/lessons/domain lib/features/lessons/presentation lib/features/lessons/providers lib/features/onboarding/presentation lib/features/reports/data lib/features/reports/presentation lib/features/reports/providers lib/features/rewards/presentation lib/features/settings/presentation && touch lib/app/app.dart lib/app/router/app_router.dart lib/app/theme/app_colors.dart lib/app/theme/app_text_styles.dart lib/app/theme/app_theme.dart lib/core/constants/app_constants.dart lib/core/utils/result.dart lib/core/utils/validators.dart lib/core/widgets/app_scaffold.dart lib/core/widgets/app_text_field.dart lib/core/widgets/loading_view.dart lib/core/widgets/primary_button.dart lib/features/analysis/data/analysis_repository.dart lib/features/analysis/domain/analysis_request.dart lib/features/analysis/domain/analysis_result.dart lib/features/analysis/presentation/analysis_history_screen.dart lib/features/analysis/presentation/analysis_result_screen.dart lib/features/analysis/presentation/analysis_type_screen.dart lib/features/analysis/presentation/analyzing_screen.dart lib/features/analysis/presentation/ask_duki_screen.dart lib/features/analysis/presentation/extended_explanation_screen.dart lib/features/analysis/presentation/paste_link_screen.dart lib/features/analysis/presentation/paste_text_screen.dart lib/features/analysis/presentation/recommendation_screen.dart lib/features/analysis/presentation/upload_capture_screen.dart lib/features/analysis/providers/analysis_provider.dart lib/features/auth/data/auth_repository.dart lib/features/auth/presentation/forgot_password_screen.dart lib/features/auth/presentation/login_screen.dart lib/features/auth/presentation/register_screen.dart lib/features/auth/presentation/verify_account_screen.dart lib/features/auth/providers/auth_provider.dart lib/features/home/presentation/home_kids_screen.dart lib/features/home/presentation/home_teens_screen.dart lib/features/lessons/data/lessons_repository.dart lib/features/lessons/domain/lesson.dart lib/features/lessons/presentation/lesson_detail_screen.dart lib/features/lessons/presentation/lesson_library_screen.dart lib/features/lessons/presentation/mandatory_lesson_1_screen.dart lib/features/lessons/presentation/mandatory_lesson_2_screen.dart lib/features/lessons/presentation/mandatory_lesson_3_screen.dart lib/features/lessons/presentation/reward_screen.dart lib/features/lessons/providers/lessons_provider.dart lib/features/onboarding/presentation/intro_duki_screen.dart lib/features/onboarding/presentation/navigation_tutorial_screen.dart lib/features/onboarding/presentation/splash_screen.dart lib/features/onboarding/presentation/welcome_screen.dart lib/features/reports/data/reports_repository.dart lib/features/reports/presentation/confirm_report_screen.dart lib/features/reports/presentation/report_form_screen.dart lib/features/reports/presentation/report_platform_tutorial_screen.dart lib/features/reports/presentation/report_sent_screen.dart lib/features/reports/presentation/reports_history_screen.dart lib/features/reports/providers/reports_provider.dart lib/features/rewards/presentation/achievements_screen.dart lib/features/rewards/presentation/progress_profile_screen.dart lib/features/rewards/presentation/shop_screen.dart lib/features/settings/presentation/account_deleted_screen.dart lib/features/settings/presentation/delete_account_screen.dart lib/features/settings/presentation/help_support_screen.dart lib/features/settings/presentation/logout_screen.dart lib/features/settings/presentation/manage_data_screen.dart lib/features/settings/presentation/privacy_policy_screen.dart lib/features/settings/presentation/privacy_screen.dart lib/features/settings/presentation/profile_screen.dart lib/features/settings/presentation/settings_screen.dart lib/features/settings/presentation/terms_screen.dart
```

## Recomendación rápida

- Empiecen por: `app/`, `core/widgets/`, `auth/`, `onboarding/`, `lessons/`, `home/`, `analysis/`.
- `reports/`, `rewards/` y `settings/` pueden arrancar con pantallas placeholder.
- No metan lógica API en las screens; usen `providers/` + `repositories/`.
