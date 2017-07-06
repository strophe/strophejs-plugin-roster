# strophejs-plugin-roster

strophe.roster.js is a plugin to provide Roster Versioning
([XEP-0237](https://xmpp.org/extensions/xep-0237.html)).

## Install

    npm install strophejs-plugin-roster


## Usage

Make sure you include [Strophe](https://www.npmjs.com/package/strophe.js) first.

You should first initialize and authorize the plugin, then you can subscribe to presence updates for the people in your roster.

### Init connection

    # `connection` is Strophe.Connection
    connection.roster.init(connection)

    var roster;
    connection.roster.get(function (result) {
      roster = result;
    });

### Subscribe to updates

    # a jid from your roster
    var jid = 'username@your_xmpp_server';

    // Subscribe to updates for the given JID
    connection.roster.subscribe(jid, 'Online', 'Nick');

    // Authorize the given JID to get updates from you
    connection.roster.authorize(jid, 'Online');

### Update nick

    connection.roster.update(jid, 'My Nick');


## API

### `.authorize(jid, message)`
### `.subscribe(jid, message, nick)`
### `.unsubscribe(jid, message)`
### `.add(jid, name, groups, callback)`
### `.update(jid, callback)`
### `.remove(jid, callback)`
### `.findItem(jid)`
### `.removeItem(jid)`
