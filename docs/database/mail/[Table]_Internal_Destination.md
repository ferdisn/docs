# [Table] Internal Destionation
## General

| Attribute | Value | Description |
| - | - | - |
| Table Name | `internal_destionations` | Store email addresses hosted on Postfix |

## Properties (Columns)

| Property | Type | Description |
| - | - | - |
| `id` | int | Object identifier |
| `alias_id` | int | Reference alias identifier |
| `internal_mailbox_id` | int | Reference mailbox identifier |

## Relationship 

| Model | Property Connector | Type | Description |
| - | - | - | - |
| [Alias]([Table]_Alias.md) | `alias_id` | Many to One | Refer to full alias configured in Postfix |
| [Mailbox]([Table]_Mailbox.md) | `internal_mailbox_id` | Many to One | Refer to mailbox in Postfix |

## SQL Enforcing Feature

| Feature | Property | SQL | Description |
| - | - | - | - |
| Presence of Surrogate Key | `id` | Primary Key, Not Null  | - |
| Presence of Object | `alias_id`,`internal_mailbox_id` | Not Null | - |
| Uniqueness of Object | `alias_id`,`internal_mailbox_id` | Unique | - |
| Presence of Parent Object | `alias_id`,`internal_mailbox_id` |  Foreign Key | - |
| Obligation to have Parent Object | `alias_id`,`internal_mailbox_id` | Not Null | - |