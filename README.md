# VS Code extension for the Kaylee modelling language

This extension is a toy/proof-of-concept project for a
modelling language I'm working on.

It aids in modelling entity relationships in such a way
that a code generator may generate appropriate
representations in your language of choice.

*Code generators are not included here, this is purely a syntax highlighting extension.*

## Known Issues

*n/a*

## Release Notes

### 0.0.5

- Added support for the `computed = <true|false>` property on fields.
- Added support for `unique(FieldA, FieldB, ...)` keys.
- Added snippets to make it easier to scaffold `schema`, `entity`, `unique`, `reference` and `mutation`.
- Enabled comments to be used in the field property block.

### 0.0.4

- Migrated to new branch name `main`.
- Corrected repository URL.

### 0.0.3

- Added support for the `TINYINT` data type.
- Added support for hexadecimal numeric literals, i.e. `0x1F`.

### 0.0.2

Added support for `mutations`, i.e.:

```kaylee
entity User {
  fields {
    UserId GUID {
      default = NEWID();
    }
    FirstName? TEXT(100);
    LastName? TEXT(100);
    ContactEmail? TEXT(254);
    ContactPhone? TEXT(50);
    Verified BIT {
      default = 0;
    }
  }

  mutations {
      Name(FirstName, LastName);
      ContactInformation(ContactEmail, ContactPhone);
      Verified(Verified);
  }
}
```

### 0.0.1

Initial release, with support for the most basic constructs like:
- Schemata
  - Entities
    - Fields
      - Types
      - Default values
      - Optional fields
    - Keys
      - Primary
      - Reference