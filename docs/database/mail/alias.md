# [Table] Alias
## General

| Attribute | Value | Description |
| - | - | - |
| Table Name | `aliases` | Store aliases |

## Properties (Columns)

| Property | Type | Description |
| - | - | - |
| `id` | int | Object identifier |
| `domain_id` | int | Reference domain identifier |
| `user` | varchar | Local portion of the alias, e.g. `user@domain.TLD` |

## Relationship 

| Object | Property Connector | Type | Description |
| - | - | - | - |
| [Domain](domain.md) | `domain_id` | Many to One | Refer to `domain.TLD` part of any accepted domains in Postfix |

## SQL Enforcing Feature

| Feature | Property | SQL | Description |
| - | - | - | - |
| Presence of Surrogate Key | `id` | Primary Key, Not Null  | - |
| Presence of Object | `user` | Not Null | - |
| Uniqueness of Object | `user`,`domain_id` | Unique  | - |
| Presence of Parent Object | `domain_id` |  Foreign Key, Not Null | - |
