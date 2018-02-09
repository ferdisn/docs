# [Table] Mailbox
## General

| Attribute | Value | Description |
| - | - | - |
| Table Name | `mailboxes` | Store mailboxes |

## Properties (Columns)

| Property | Type | Description |
| - | - | - |
| `id` | int | Object identifier |
| `domain_id` | int | Reference domain identifier |
| `user` | varchar | Local portion of the alias, e.g. `user@domain.TLD` |
| `password` | varchar | SHA512 of user password |

## Relationship 

| Model | Property Connector | Type | Description |
| - | - | - | - |
| [Domain]([Table]_Domain.md) | `domain_id` | Many to One | Refer to `domain.TLD` part of any accepted domains in Postfix |

## SQL Enforcing Feature

| Feature | Property | SQL | Description |
| - | - | - | - |
| Presence of Surrogate Key | `id` | Primary Key, Not Null  | - |
| Presence of Object | `domain_id`,`user` | Not Null | - |
| Uniqueness of Object | `domain_id`,`user` | Unique | - |
| Presence of Parent Object | `domain_id` |  Foreign Key | - |
| Obligation to have Parent Object | `domain_id` | Not Null | - |