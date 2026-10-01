# GUS collection design review

Source visual truth: /Users/gus/Documents/Codex/2026-10-01/need-this-done/outputs/TGES Brand Preview/GUS Experience Education and Sports.png

Implementation evidence:
- /Users/gus/Documents/Codex/2026-10-01/need-this-done/work/product-qa/desktop-home.png
- /Users/gus/Documents/Codex/2026-10-01/need-this-done/work/product-qa/desktop-sports.png
- /Users/gus/Documents/Codex/2026-10-01/need-this-done/work/product-qa/mobile-sports.png

The reference is a 1697 x 927 brand board, not a website wireframe. Desktop evidence uses 1440 x 1000 CSS viewport; mobile evidence uses 390 x 844. Saved desktop capture is 1440 x 948 pixels due the browser's visible capture region; mobile capture is 390 x 844. Compared at equal displayed width for overall art direction, not a pixel overlay. The UI adapts the board into an existing storefront and coaching page.

## Findings and fixes
- P2: Desktop Parent Playbook navigation inherited navy on navy. Changed the header to white, replaced the temporary text mark with the generated image wordmark and explicitly set navy navigation. Post-fix desktop screenshot shows every link.
- P2: Lazy-loaded product images shifted the TGES Sports anchor. Added intrinsic width/height and stable aspect ratios. Post-fix mobile DOM reports sports top 108px and width 390px with no horizontal overflow. Screenshot confirms heading below the sticky header.
- P2: Interim Playbook cover lacked the reference court detail. Replaced it with an inspected flat cover matching the board, including grayscale basketball court, correct title and navy/orange display type. Rendered final PDF cover inspected in work/product-qa/playbook-1.jpg. Existing 16 interior pages preserve all manuscript text and tables, with updated color operators.

## Surface review
Typography: Barlow Condensed bold/italic follows the condensed sports-inspired reference. Inter/system body copy remains readable. Headings wrap without clipping at desktop and phone sizes. PDF worksheets use embedded Barlow Condensed and Arial.
Spacing: roomy white education layout, navy sports section, 1180px content width, balanced product image/copy columns. Mobile columns stack. No horizontal overflow at 1440px or 390px.
Colors: navy #071D3B, orange #F58426, white. Darker orange for text on white maintains contrast. No nonprofit green. No white button labels on the orange background.
Images: generated education and sports mockups match the board; compressed WebP for web delivery. Product images are explicitly identified as concepts. Final public book samples come from the actual refreshed PDF. No fabricated stock or tournament dates.
Copy: current $19 Playbook and $300/$425 coaching offers retained. Planner has a four-page free preview and interest email, without an unconfigured paid checkout. Sports plans described as in development.

## Interactions and checks
- Mobile menu opens, navigation closes it, TGES Sports scrolls to the correct section.
- Desktop Parent Playbook link opens the product page.
- Book sample link opens the samples section; all three real-page images load.
- Planner sample and existing free PDFs are present and parse as PDF documents.
- Required product-license checkbox remains in place. Stripe destinations match the existing site. No checkout purchase or live signup was submitted.
- Build passes; all four existing compatibility tests pass.
- Browser console checked for errors/warnings: none reported during local page review. Third-party video playback was not exercised.
- Only sample/free PDFs belong in public deployment. Full owner Playbook, planner and focus plans stay outside the public repository.

## Follow-up polish
Generated logo/cover artwork still needs printer-specific proofing before commercial print production. No print order placed. A physical book image does not represent shipped stock.

Final result: passed

## Live publication, October 1, 2026
Published at https://gusexperience.org/ through GitHub Pages, production commit 6567c53. All 19 published files match the reviewed build byte for byte. Live homepage and TGES Sports verified in Chrome. Sports heading settles 108px below the viewport top. No broken images found. Screenshots saved in outputs/GUS Website Live.png and outputs/TGES Sports Live.png.

## Sports page and original identity revision
TGES Sports now lives at /sports/ with direct-load HTML, page-specific metadata, and a navigation link. No sports section or apparel image renders on the homepage. Original logo restored in header/footer, original basketball illustration restored in homepage hero. Desktop and mobile browser checks found no overflow or broken images. Sports-to-home Planner navigation works. Build passed. Final result: passed.
