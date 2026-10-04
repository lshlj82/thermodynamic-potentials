# Free Energy, Interactively

An interactive, single-page web demo of the thermodynamic potentials: enthalpy, the Helmholtz and Gibbs free energies, and the grand free energy; free energy as available work and as a force toward equilibrium; the thermodynamic identities, the thermodynamic square, and Maxwell relations; extensive and intensive quantities; and the link between the Gibbs free energy and the chemical potential.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee** (Statistical Physics 1, Chapter 5, Free Energy and Chemical Thermodynamics, Sections 5.1 and 5.2). It follows the demo for Chapter 4 (engines and refrigerators).

## What's inside

**Free energy as available work.** H = U + PV, F = U − TS, and G = U − TS + PV, with the magician-and-rabbit interpretation. An energy budget for creating one mole of a monatomic gas at any temperature and pressure shows U, PV, and TS as a waterfall and the four potentials in the U–H–F–G square, confirming that G/N equals the chemical potential of Section 3.5. ΔF ≤ W and ΔG ≤ W<sub>other</sub>, with a note on the Jarzynski equality, and the energy budget of splitting water by electrolysis and running a hydrogen fuel cell (ΔH = 286 kJ, ΔG = 237 kJ, TΔS = 49 kJ).

**Thermodynamic identities and Maxwell relations.** An interactive thermodynamic square ("Very Fat Ugly SHeeP"): choose U, H, F, or G to see its identity, natural variables, partial-derivative formulas, and Maxwell relation (Problem 5.12), with the natural variables highlighted on the square. C<sub>P</sub> − C<sub>V</sub> = TVβ²/κ<sub>T</sub> (Problem 5.14) for water (about 1%), mercury (about 13%), and an ideal gas (exactly R per mole).

**Free energy as a force toward equilibrium.** dS<sub>total</sub> = −dF/T at fixed T and V, and −dG/T at fixed T and P. A two-level system of 100 particles shows U, −TS, and F against the number excited, with the minimum of F moving from all-ground at low temperature toward half-excited at high temperature, matching N/(e<sup>ε/k<sub>B</sub>T</sup> + 1). A sorting game for extensive and intensive quantities (Problem 5.21).

**Gibbs free energy and chemical potential.** G = Nμ, and μ(T, P) = μ° + k<sub>B</sub>T ln(P/P°) for an ideal gas (Problem 5.22), plotted alongside the explicit formula. The grand free energy Φ = U − TS − μN = −PV (Problem 5.23), applied to a proton in the Sun's atmosphere: at 5800 K the hydrogen atom has Φ = −4.7 eV, more stable than the bare proton, and the two are equally stable at about 8600 K for the given electron density (both adjustable).

## Running it

There is nothing to build or install. The whole demo is one self-contained file, `index.html`, with all CSS and JavaScript inline.

Open it locally by double-clicking `index.html`, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

### Publishing with GitHub Pages

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select your main branch and the `/ (root)` folder, then save.
4. After a minute or so, the demo will be live at `https://<your-username>.github.io/<repository-name>/`.

## Technical notes

- Plain HTML, CSS, and vanilla JavaScript drawn on `<canvas>`. No frameworks, no build step.
- The energy budget uses the Sackur–Tetrode entropy; for helium at 298 K and 1 bar, U = 3.7 kJ, PV = 2.5 kJ, TS = 37.6 kJ, so F = −33.9 kJ and G = −31.4 kJ, and G/N = μ = −0.326 eV.
- The two-level system's entropy is S = k<sub>B</sub> ln C(N, n), computed exactly.
- The solar example solves Φ<sub>occupied</sub> = 0 exactly (about 8600 K). The lecture's estimate of about 8800 K holds the temperature inside the logarithm at 5800 K.
- C<sub>P</sub> − C<sub>V</sub> uses the textbook's room-temperature data for water and mercury (Problem 1.46).
- Long equations wrap on narrow screens.
- Equations are typeset with [MathJax 3](https://www.mathjax.org/) (SVG output, loaded from cdnjs), so they need no extra web fonts.
- The only other external resources are the Newsreader and Instrument Sans fonts from Google Fonts, with system font fallbacks if they fail to load.
- Opening the page requires an internet connection for MathJax; offline, the equations appear as raw TeX.
- Supports light and dark mode via `prefers-color-scheme`, and is responsive down to phone widths.

## Caveats

- The energy budget treats the gas as monatomic and ideal.
- The solar example neglects excited states of hydrogen and the electron's spin states, as the problem does.

## Credits

- Demo: Claude Opus 5.5
- Physics content and examples: lecture notes by Sang Hoon Lee
- The lecture follows Daniel V. Schroeder, *An Introduction to Thermal Physics* (Sections 5.1 and 5.2 and Problems 5.12, 5.14, and 5.21 to 5.23).
- Jarzynski equality: C. Jarzynski, "Nonequilibrium Equality for Free Energy Differences," *Physical Review Letters* 78, 2690 (1997).

## License

No license has been chosen yet. Add a `LICENSE` file (for example, MIT or CC BY 4.0) before sharing or reusing this project publicly, and confirm that any use of the lecture material is permitted by its author.
