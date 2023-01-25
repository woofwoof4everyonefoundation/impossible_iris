# impossible_iris

original can be found at:

https://nvk.org/n00b-nip5

extracted instructions follow:

"NIP5: Mapping Nostr keys to DNS-based internet identifiers"

    Buy a domain 😅
    Setup Domain DNS records to point to GitHub Pages:

      
    | Type | Host           | Answer          | TTL | Priority |
    |------|----------------|-----------------|-----|----------|
    | A    | YOURDOMAIN.COM | 185.199.108.153 | 300 |          |
    | A    | YOURDOMAIN.COM | 185.199.109.153 | 300 |          |
    | A    | YOURDOMAIN.COM | 185.199.110.153 | 300 |          |
    | A    | YOURDOMAIN.COM | 185.199.111.153 | 300 |          |

    Create a new github repo github.com/new
    Create a new file your-repo/.well-known/nostr.json
    Edit nostr.json to reflect YOUR pub key (hex format) and desired nickname this content:

    {
      "names": {
        "bob": "e88a691e98d9987c964521dff60025f60700378a4879180dcbbb4a5027850411"
      }
    }
      

    Create a new file in the root folder _config.yml and add this line

    include: [".well-known"]

    Navigate to github.com/[USER]/[YOUR-REPO]/settings/pages
    Under "Build and deployment" select "Deploy from branch" then below select "Main/Master" branch
    Under "Custom domain" type your naked YOURDOMAIN.COM (github might complain, ignore)
    Below it, check Enforce HTTPS. Sometimes this may take a few minutes to be available.
    Then head over branle.netlify.app/settings or astral.ninja/settings (using an extension like Alby or nos2x)
    edit the NIP-05 Indentifier field to reflect "bob@YOURDOMAIN.com" and press Save
    you are all set now, enjoy the vanity address.
