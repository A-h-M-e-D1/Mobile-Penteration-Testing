### What are Application Components?
---

- Building blocks that define different parts of an Android application.

- Declared inside AndroidManifest.xml.

- Can work individually or together.

- Main types:
  1. Activities

  2. Services

  3. Broadcast Receivers

  4. Content Providers

### What is IPC (Interprocess Communication)?

- A mechanism that allows different applications or processes to communicate and share data.

- Main mechanisms: Intents, Binder, Broadcasts, and Content Providers.

Example:
```txt
When WhatsApp requests to read contacts, it asks for the
READ_CONTACTS permission.  
After the user accepts, WhatsApp uses the Contacts app’s
Content Provider to read and display your contacts.
```