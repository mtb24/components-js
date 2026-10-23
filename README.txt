LiveKit boolean scroll-anchor evidence — October 23, 2026
Code commit: 6afb6193a6766f33ba6725f2200e3ae6a91d6b44
Base commit: 65701808b070bfdbba6627a5758dd13988b0141b

Before: current main with the real AgentChatTranscript and MessageScroller;
scrollAnchor=true marks 0/7 messages as anchors, while any marks 7/7.
After: both mark 7/7 and position the appended message identically.
Screenshots use a local fixture with DOM-derived anchor counts/positions.
No room connection, microphone, or credentials are required.
Mobile image uses the built BooleanScrollAnchor Storybook story at 390px width.

Eight new regression cases: true, any, false, omitted, user, other, mounted
prop updates, and the unanchored thinking indicator. Baseline: 2 fail, 6 pass.
Fixed: all 8 pass. Full repository: 494 tests pass.
Build, lint, formatting, and configured API checks pass. Separate agents-ui
TypeScript check retains exactly 12 baseline diagnostics, with none added.
