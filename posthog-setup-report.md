<wizard-report>
# PostHog post-wizard report

The wizard has completed a deep integration of your DevEvent app with PostHog analytics. The project already had PostHog initialized via `instrumentation-client.ts` (Next.js 15.3+ pattern) and reverse-proxy rewrites configured in `next.config.ts`. Three client-side events were already instrumented across the component layer. The wizard verified the implementation matches PostHog best practices, confirmed environment variables are set, validated no TypeScript or lint errors exist, and created a PostHog dashboard with five insights.

| Event Name | Description | File |
|---|---|---|
| `nav_link_clicked` | Fired when a user clicks a navigation link in the header navbar. Includes `label` property. | `components/Navbar.tsx` |
| `explore_events_clicked` | Fired when a user clicks the "Explore Events" CTA button on the home page. | `components/ExploreBtn.tsx` |
| `event_card_clicked` | Fired when a user clicks on a featured event card. Includes `event_title`, `event_slug`, `event_location`, `event_date` properties. | `components/EventCard.tsx` |

## Next steps

We've built some insights and a dashboard for you to keep an eye on user behavior, based on the events we just instrumented:

- [Analytics basics (wizard) — Dashboard](https://us.posthog.com/project/479119/dashboard/1739763)
- [CTA Clicks Over Time](https://us.posthog.com/project/479119/insights/ewSTfNgX)
- [Event Card Clicks Over Time](https://us.posthog.com/project/479119/insights/QOXd2gV6)
- [Discovery Funnel: Explore → Event Click](https://us.posthog.com/project/479119/insights/jEzkT1dQ)
- [Most Clicked Events (by title)](https://us.posthog.com/project/479119/insights/e0BJ4A2z)
- [Navigation Link Clicks by Label](https://us.posthog.com/project/479119/insights/EcruhA1V)

## Verify before merging

- [ ] Run a full production build (the wizard only verified the files it touched) and fix any lint or type errors introduced by the generated code.
- [ ] Run the test suite — call sites that were rewritten or instrumented may need updated mocks or fixtures.
- [ ] Add `NEXT_PUBLIC_POSTHOG_PROJECT_TOKEN` and `NEXT_PUBLIC_POSTHOG_HOST` to `.env.example` and any bootstrap scripts so collaborators know what to set.
- [ ] Wire source-map upload (`posthog-cli sourcemap` or your bundler's upload step) into CI so production stack traces de-minify.

### Agent skill

We've left an agent skill folder in your project. You can use this context for further agent development when using Claude Code. This will help ensure the model provides the most up-to-date approaches for integrating PostHog.

</wizard-report>
