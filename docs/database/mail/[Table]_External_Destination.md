# [Table] External Destionation
## General

| Attribute | Value | Description |
| - | - | - |
| Table Name | `external_destionations` | Store email addresses not hosted on Postfix |

## Properties (Columns)

| Property | Type | Description |
| - | - | - |
| `id` | int | Object identifier |
| `alias_id` | int | Reference alias identifier |
| `external_email_address` | varchar | Full address of destination alias in form of  `user@domain.TLD` |

## Relationship 

| Model | Property Connector | Type | Description |
| - | - | - | - |
| [Alias]([Table]_Alias.md) | `alias_id` | Many to One | Refer to full alias configured in Postfix |

## SQL Enforcing Feature

| Feature | Property | SQL | Description |
| - | - | - | - |
| Presence of Surrogate Key | `id` | Primary Key, Not Null  | - |
| Presence of Object | `alias_id`,`external_email_address` | Not Null | - |
| Uniqueness of Object | `alias_id`,`external_email_address` | Unique | - |
| Presence of Parent Object | `alias_id` |  Foreign Key | - |
| Obligation to have Parent Object | `alias_id` | Not Null | - |