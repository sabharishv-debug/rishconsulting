<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->

## Project rules
- All site copy, contact details, nav, service data, image paths and demo data live in `src/content/*.ts`; components read from there so the owner edits text in one place.
- Contact form submits via `submitEnquiry` server function (`src/lib/contact.functions.ts`): it emails via the Resend connector gateway when `RESEND_API_KEY` is linked, and always saves to `public.enquiries` with the admin client (table allows public insert, no public read).
- The 3D globe (three / @react-three/fiber) is lazy-loaded behind `ClientOnly` so it never runs during SSR.
- Globe interaction uses Three.js OrbitControls with bounded zoom and no pan, keeping the map centered and supporting mouse and touch without custom gesture logic.
- Any illustrative number in the UI must sit inside a `DemoPanel` (shows the "Illustrative demo" badge).
