# Enterprise v2 verification

- Browser: login/signup stay in the same DOM; country selection changes flag and calling code; complete phone/OTP enables each action; OTP focus follows the selected digit.
- Browser: location search filters rows and clearing restores all four results; selecting a map marker changes active color, route, and branch card; only Pick up here confirms it.
- Browser: empty calendar selects a range; time tabs update the existing panel; sun and arc follow time and sky color transitions.
- Browser: class/sort/seats filters select correctly and Show Cars first shows the loading state.
- Browser: insurance, extra services and payment methods release the previous green state; child-seat quantity updates totals.
- Browser: booking flow through driver details, review, price bottom sheet, payment and confirmation works; fixed review footer has a 64px height and a single-line amount.
- Browser: profile scrolls inside the app while navigation remains at the viewport bottom; outer viewport has no scrolling.
- Browser: confirmation includes the existing checkmark illustration, animated ring/stars, and an audio chime scheduled by the payment button gesture.
- Browser: all 37 route states loaded with no missing images and no outer-page scrolling.
- Automated: 13 pricing, date and phone validation checks pass, including cross-month rental length and different car daily rates.
- Automated: all 461 local image references in 37 source frames resolve to non-empty files; raster references use WebP; no temporary Figma URLs remain.
- Assets: 15 PNGs converted to WebP, from 15,614,242 bytes to 1,432,424 bytes (90.8% smaller). SVG icons remain vectors.
- Figma: current design context and screenshots retrieved for map, car details and evening selection. Complete nested text traversal read 788 text nodes from 36 current prototype frames; 674 matching exported text nodes have explicit runtime typography, with the exported layout retained. The existing cleared-filter state remains available from the prior prototype export.
- Browser v2.1: verified original map pins, only one visible route per destination, route origin at the fixed person marker, and no navigation on pin selection.
- Browser v2.1: verified OTP digit 4 has the green 4px ring while digit 1 has no shadow; driver mobile control is neutral before focus and green only during focus.
- Browser v2.1: verified car-detail price lines have non-overlapping 26px and 16px line boxes; opaque location background is #f3f3f3; night gradient, white moon and arc use original Figma colors.
- Automated v2.1: 13 state checks pass, including isolating rental-rate totals from later insurance selections.

Native mobile keyboard and audible playback remain browser/OS controlled. No physical-phone hardware test was performed. Remote services remain demo integrations.

- Final browser pass: all 37 route states rendered without missing images or outer scrolling. Verified the 17-day detail total of $2,084.54 with distinct 26px/16px line boxes.

### v2.2 verification
- Browser: edit bounds remain inside the location field; summary truncates within its available width. Model/spec rows have additional spacing.
- Browser: mouse drag moved quick-chip scrollLeft from 0 to 99; native touch horizontal overflow is enabled. No filter toggled during the drag.
- Browser: filters render as a modal dialog with an inert car-list underlay, slide in from the bottom, close back to results, and the results back button returns Home. Clear All and Show Cars preserve the loading transition.
- Browser: Continue as guest opens an empty search; Find a car shows Action Required with the pickup warning. Selecting Munich Central station automatically opens the empty date modal, selecting 9–17 May and Choose times opens the time panel.
- Browser: View my rental on confirmation opens Profile.
- Automated: syntax, all 13 state checks, and all 461 local image references pass. Touch scrolling uses the native browser behavior; physical-phone hardware was not tested.

### v2.3 viewport verification
- Replaced width-only zoom and variable canvas height with a fixed 393×852 logical frame fitted uniformly to the safe visible browser area. VisualViewport resize/scroll and pageshow update the fitting; pinch zoom keeps its native behavior.
- Browser: iframe viewports 393×640, 390×664, 393×720 and 393×852 show the whole frame; logical height stays 852, and outer viewport scrollHeight equals clientHeight. Changing simulated visible height from 720 to 640 and back to 852 refits the frame without reflowing its geometry.
- Browser: home, login, OTP, results, details, location, map, empty calendar, time, filters, review, payment and confirmation fit in the 640px viewport. Bottom navigation and review confirmation bar remain inside the frame. Country menu stays aligned in the scaled frame.
- Browser: desktop stage remains exactly 393×852. Mobile dimensions were simulated in browser iframes; physical Safari/Chrome browser chrome and hardware keyboard behavior were not tested on a phone.
- Automated: seven viewport cases (including landscape) preserve aspect ratio, fit within both bounds and fill the limiting edge; all existing pricing/date/phone checks and 461 image references pass.

### v2.4 mobile keyboard verification
- Supersedes the v2.3 mobile contain/letterbox approach: mobile scales by width only and uses the visible viewport for the logical content height. Desktop retains its 393×852 reference.
- Browser: 393×720 and 393×400 stages both have exactly 393px width, no left/right gutter, matching visible height, and no outer viewport scrolling. A 390×664 results frame also fills its width and height.
- Browser: OTP focus moves to digit six; Verify is visible in a 400px viewport and Change phone number remains reachable by the form's internal scroll. The phone field and country popup are accessible in the short viewport; the popup can scroll and remains inside it.
- Browser: results header and first card heading remain visible; list uses the remaining viewport height. Reviewed home, driver, date/time, filter, review, details, extras, protection and confirmation viewport geometry.
- Automated: 25 mobile/keyboard cases preserve width scale across height changes, plus seven desktop reference cases and all existing pricing/date/phone/image checks.
- Limit: keyboard space was simulated in browser iframes; no physical Android/iPhone hardware test was performed.

- Final check: mobile Home branding scrolls with its hero and does not cover AI input when focused in the short viewport; desktop login stage remains 393×852.
