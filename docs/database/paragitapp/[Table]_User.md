# [Table] User
## General

| Attribute | Value | Description |
| - | - | - |
| Table Name | `users` | Store users |

## Properties (Columns)

| Property | Type | Description |
| - | - | - |
| `id` | int | Object identifier |
| `first_name` | varchar | First portion of user |
| `middle_name` | varchar | Middle portion of user |
| `last_name` | varchar | Last portion of user |
| `batch_year` | int | Year of first membership |
| `birth_date` | date | Date of birth |
| `voice_type` | varchar | Type of voice |
| `email` | varchar | Member email address as username |
| `password` | varchar | BFH of user password |
| `password_dovecot` | varchar | SHA512 of user password |
| `remember_token` | varchar(100) | Laravel column for 'Remember Me' Feature |
| `created_at` | timestamp | Laravel column for Object manipulation |
| `updated_at` | timestamp | Laravel column for Object manipulation |

## Relationship 

| Model | Property Connector | Type | Description |
| - | - | - | - |
| [Code]([Table]_Code.md) | `voice_type` | Many to One | Refer to `code_name` column by `code_group = 'VOICE_TYPE'` as allowable voice type definition |

## SQL Enforcing Feature

| Feature | Property | SQL | Description |
| - | - | - | - |
| Presence of Surrogate Key | `id` | Primary Key, Not Null  | - |
| Presence of Object | `email` | Not Null | - |
| Uniqueness of Object | `email` | Unique | - |
| Presence of Parent Object | `voice_type` |  Foreign Key | - |
| Obligation to have Parent Object | `voice_type` | Not Null | - |