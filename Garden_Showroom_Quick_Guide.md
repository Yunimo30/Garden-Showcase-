# Garden Showroom Quick Guide

Use this guide to manage outfits, update the physical stand mannequins, and help visitors browse the garden. Day-to-day outfit changes happen inside the game; you do not need to edit scripts.

## Create your first outfit

1. Join the published game using an account with owner or administrator access.
2. Open **Manage Showroom**, choose **Outfits**, and select a stand. Search by its **StandID** or outfit name. You can also approach a stand and choose **Manage Stand**.
3. In the **Outfit Workshop**, select **Import Outfit**.
4. Choose **Import Player Outfit**, enter the player's numeric **Roblox UserId**, give the outfit a name, and choose **Import & preview**. Use the number from the player's profile URL, not their username or display name.
5. Inspect the preview. Remove or replace unwanted items, or use **+ Add Item** to add another accessory or clothing item.
6. Choose **Save Draft** and wait for the success message.
7. Choose **Publish**, enter **PUBLISH** when asked, and confirm. Wait for the successful publication message.
8. Visit that stand. Its public outfit and physical mannequin should now show your published look.

**Imported player outfits are snapshots.** If that player changes their avatar later, your saved showroom outfit stays the same. Import again if you want their newer look.

## Understand the three save actions

| Action | What it changes |
| --- | --- |
| **Save Draft** in management | Saves your private working outfit. Visitors and the public mannequin keep seeing the existing published assignment. |
| **Publish** in management | Makes the reviewed outfit public on the selected stand and updates its mannequin. |
| **Save Outfit** in the public viewer | Opens Roblox's prompt to save the look to the visitor's own Roblox outfits. It does not edit the showroom. |

**Studio publishing is separate.** File → Publish to Roblox releases changes to the game's scripts, map, or UI. Routine in-game outfit publication does not require republishing the Studio place.

## Import and edit a look

The import method can also use a **Roblox Outfit ID**, **Capture My Current Outfit**, or individual supported avatar **Asset IDs**. These are different ID types. A bundle ID or clothing template ID is not interchangeable with an avatar asset ID. Prefer R15 for layered clothing.

In the Workshop:

- **Inventory** groups the outfit's items by category. Filtering only changes the list you see; it does not remove items from the outfit.
- **+ Add Item** accepts a supported asset ID or Roblox catalog URL, or lets you search the catalog. Choose **Validate & add item** when entering an ID.
- **Remove** takes an item out of the working outfit. **Replace** looks for a compatible replacement for that item.
- **Appearance** contains body colors, supported proportions, and outfit details. Use a six-digit hex color such as `E8C5AB`. Choose **Apply outfit details** after editing details in that panel.
- **Undo** and **Redo** step through recent edits. **Reset to Imported** returns to the original imported look after confirmation.
- Rotate the preview to inspect accessories and layered clothing before saving.

Edits stay private until you save and publish. Save a draft before leaving the server. On phones, switch between **Stands**, **Preview**, and **Inventory**, and scroll to reach additional controls.

## Find and maintain stands

The showroom has **100 stands**, with 20 in each district: Pavilion Garden, Willow Pond, Overgrown Ruins, Flower Terrace, and Woodland Grove.

Use the district and status filters to find empty or configured stands. Check the exact StandID before publishing. **Go to Stand** takes you near the selected stand without moving its geometry.

To remove a public outfit, use the management dashboard's **Clear Assignment** action and confirm with **CLEAR**. This empties the assignment while retaining the stand and its identity.

To recover an earlier assignment, open that stand's **History**, review the previous outfit, and confirm **RESTORE**. Restoration creates a new revision and checks that the outfit is still valid. Keep your own record of important outfit sources as an additional reference.

If another editor updates a stand, reload the latest assignment and review it before saving again. A revision conflict protects their changes from being silently overwritten.

## Browse outfits as a visitor

Approach a configured stand and use **Browse Outfit**. The viewer offers:

- **View Items** to inspect the outfit's individual items, categories, prices, and ownership information where available.
- **Try On** to temporarily apply the look to your character. Use the restore control to return to your previous appearance.
- **Save Outfit** to open Roblox's own outfit-saving prompt. Wait for Roblox's confirmation; opening or cancelling the prompt does not save anything.
- **Buy Items** for eligible available items, or **Buy item** inside the item list. Roblox opens the final confirmation and determines the final price. You can cancel it.

Some actions can remain unavailable for demo outfits, off-sale or limited items, items you already own, or items Roblox cannot verify. Bulk buying supports at most 20 eligible items at once. Use the individual item list where appropriate. Purchases are intentionally blocked in Studio Play.

## Explore and preferences

**Explore** travels to Central Fountain or one of the five garden districts. New arrivals spawn at the gazebo. Main Entrance is not a teleport choice.

Open **Preferences** to change Music, Sound effects, Ambient sounds, quality, particles, or weather for your session. **Music** mutes or unmutes the background playlist; playback continues while muted. **Reset defaults** restores the session defaults.

## Manage staff

Only the configured owner can manage staff. Open **Staff**, enter the person's actual Roblox username, and choose **Find & verify player**. Check the returned account and numeric UserId before confirming **GRANT**.

To remove access, confirm **REVOKE** for the correct account. Administrators can manage outfits but cannot grant staff access or change the configured owner.

The developer must complete the client's account or group ownership setup before handover. Owner identity cannot be changed from the management dashboard.

## Change background music in Studio

1. Open **ServerStorage → BackgroundMusic** in Explorer.
2. Add a **Sound** for each track and set its **SoundId** to `rbxassetid://YOUR_AUDIO_ID`.
3. Give each track a clear name. Tracks play in name order and the playlist repeats. Set **Volume** and **PlaybackSpeed** on each Sound as needed.
4. Make sure Roblox permits that audio to play in this experience. Test in Play and then in the published game.
5. Save and publish the Studio update when you are ready to release the new playlist.

You do not need to start the source Sounds manually. The music system handles playback and connects it to the Music preference.

## Common problems

| Problem | What to do |
| --- | --- |
| Manage Showroom is missing | Check that you joined with an authorized owner or administrator account. Ask the owner to verify access. |
| Avatar import returns HTTP 400 | Check the selected import method and numeric ID. Use a UserId for Import Player Outfit, not an asset or outfit ID. If the ID is correct, retry later and report the full error. |
| Outfit does not appear on the stand | Confirm you published the assignment, rather than only saving a draft. Check the StandID and final success message, then reopen the stand. |
| A request times out | Reload and inspect the saved assignment before repeating a write. The server may already have completed the first request. |
| Buy button is disabled | Check Studio versus the published game, item eligibility, ownership, and the displayed reason. Reopen the viewer to refresh details. |
| Music is silent | Enable Music in Preferences, check device volume, and verify the audio ID and experience permissions. |
| Changes disappear after stopping Studio Play | Studio uses temporary test storage. Test persistent outfit changes in the published Roblox game. |

## Final handover check

Before opening to players, use the published Roblox game to save and publish a test outfit, leave, and rejoin. Verify its stand and mannequin remain correct. Check mobile navigation, Try On and restore, native Save Outfit and purchase prompts, and music preferences. Cancel purchase prompts unless you intend to buy.

Keep a backup of the place and preserve **ProjectArchive**. Have the developer confirm client permissions and the intended storage configuration before switching from QA to production; changing a storage namespace does not transfer saved outfits.
