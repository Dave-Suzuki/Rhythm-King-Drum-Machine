# Rhythm Knight MK-2 Drum Machine - Project Context

## Current State: v1.00
- **Branch**: `claude/polish-drum-machine-a7hoP`
- **Tag**: `v1.00` (local)
- **Single-file app**: Everything lives in `index.html` (HTML + CSS + JS)

## Architecture
- Pure vanilla HTML/CSS/JS, no build tools or dependencies
- Web Audio API for sound synthesis (no sample files)
- All styles are inline `<style>` blocks in the HTML
- All JS is inline `<script>` at the bottom of the HTML

## Key Sections in index.html
- **CSS** (lines ~1-1750): Base styles, then `@media (min-width: 900px)` desktop overrides
- **HTML** (lines ~1750-2050): Transport bar (play/tap/knobs), section toggles, edit mode panel, pads panel, rhythm selector
- **JS** (lines ~2050+): Audio engine, sequencer, pattern editor, knob controls, section toggles

## Design Language
- Styled after the **Rhythm Knight MK-2** (inspired by vintage Maestro/Roland hardware)
- Dark charcoal knobs with white indicator lines and metallic ring borders
- Warm beige/cream body color scheme
- Hardware-authentic labels (Vol, Tone, Speed, Swing)

## Layout
- **Mobile** (<900px): Stacked layout, transport uses CSS grid (2 rows: Play+Waveform / Tap+BPM), knobs 34px
- **Desktop** (>=900px): All panels visible with collapsible sections, knobs 56px, smooth expand/collapse animations using `max-height` + `scaleY` + `cubic-bezier(0.4, 0, 0.2, 1)`

## Key Implementation Details
- Knob interaction: drag up/down mapped to slider values via `data-slider` attributes
- Section collapse: `.section-hidden` class toggles `max-height: 0` + `opacity: 0` + `scaleY(0)`
- Edit mode panel uses `max-height: 5000px` (not `none`) to preserve animation
- Rhythm categories always expanded on desktop (`.rhythm-buttons { display: grid !important }`)
- Pattern editor re-renders when edit section is opened

## Recent Polish (v1.00)
- Mobile transport grid layout: [Play][Waveform] / [Tap][BPM]
- Center-aligned waveform and BPM on mobile
- Rhythm Knight hardware-style dark knobs (replaced generic silver)
- Mobile knobs shrunk from 44px to 34px
- Desktop smooth expand/collapse with cubic-bezier easing + scaleY transform
- Fixed pattern editor close animation (was using `max-height: none`)
