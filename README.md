# 🎄 Merry Wishlist

A Christmas wishlist where you share the gifts you'd actually love, so friends can surprise you without having to ask.

## Features

- **Add a wish in seconds:** paste a link from any shop and the name and photo fill in automatically. Pick how badly you want it (Really need / Would love / Dream gift) and optionally say why. No link? Add it by name.
- **Visibility:** make your list public, visible to all your contacts, or only to friends you hand-pick.
- **No spoilers:** you never see who claimed or bought something on your own list.
- **Gift registry:** friends see what's still free, what's reserved and what's bought, so nobody doubles up.
- **Proof of purchase:** upload a receipt, or buy through a tracked link in the app and confirm afterwards.
- **Discover:** browse anyone's public list.

## Try it

Open `index.html` in a browser. Use **"Viewing as"** at the top to switch between demo people and see both the list owner's and the gift giver's side.

## Affiliate links (earning money)

When a friend taps **"Buy via link"**, the shop link is turned into a commission link. Fill in your IDs in the `AFFILIATE` block at the top of the `<script>` in `index.html`; empty values are skipped:

| Setting | Where to get it | Used for |
|---|---|---|
| `amazonTags` | [Amazon Associates](https://partnernet.amazon.nl) (one tracking ID per Amazon store) | Amazon links |
| `bolSiteId` | [Bol.com partner program](https://partner.bol.com) | Bol.com links |
| `skimlinksId` | [Skimlinks](https://skimlinks.com) | All other shops |
| `sovrnKey` | [Sovrn Commerce](https://www.sovrn.com/commerce/) | All other shops (if no Skimlinks) |

Order: Amazon / Bol first (you keep the full commission), then Skimlinks, then Sovrn, otherwise the plain link.
Before going live, check each program's current link format and terms, and keep the commission disclosure visible.

## Prototype status

Everything is stored in your browser only (no accounts or server yet). Next steps for a real app:

1. Accounts and a shared database (e.g. Supabase or Firebase).
2. Verified purchase tracking through retailer affiliate programs.
3. Server-side receipt storage, visible only to the buyer.
4. Move the link lookup to the server. It now uses [Microlink](https://microlink.io)'s free tier (about 50 lookups per visitor per day); when that fails, the name is guessed from the link itself.
