# [Table] Domain
## General

| Attribute | Value | Description |
| - | - | - |
| Table Name | `domains` | Store domains |

## Properties (Columns)

| Property | Type | Description |
| - | - | - |
| `id` | int | Object identifier |
| `domain` | varchar | Domain name after the `@` sign, e.g. `user@domain.TLD` |
| `catch_all_mailbox_id` | varchar | Reference mailbox identifier |
| `alias_for` | int | Reference domain identifier |

## Relationship 

| Model | Property Connector | Type | Description |
| - | - | - | - |
| [Mailbox]([Table]_Mailbox.md) | `catch_all_mailbox_id` | Many to Zero | Refer to existing mailbox which can accept mail in Postfix that acts as a catch all Mailbox, if not null it means this domain has catch all address |
| Domain (self) | `alias_for` | Many to Zero | Refer to existing domain for which this domain is an alias |

## SQL Enforcing Feature

| Feature | Property | SQL | Description |
| - | - | - | - |
| Presence of Surrogate Key | `id` | Primary Key, Not Null  | - |
| Presence of Object | `domain` | Not Null | - |
| Uniqueness of Object | `domain` | Unique | - |
| Presence of Parent Object | `catch_all_mailbox_id` |  Foreign Key | - |
| Obligation to have Parent Object | `catch_all_mailbox_id` | Allow Null | - |
| Presence of Parent Object | `alias_for` |  Foreign Key, Allow Null | - |
| Obligation to have Parent Object | `alias_for` | Allow Null | - |