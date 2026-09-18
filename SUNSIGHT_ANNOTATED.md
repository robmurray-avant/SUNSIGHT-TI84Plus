# SUNSIGHT — annotated source

The installable, hardware-tested calculator program is [`SUNSIGHT.8xp`](SUNSIGHT.8xp).

[`SUNSIGHT.txt`](SUNSIGHT.txt) is a human-readable rendering of the v1.1 TI-BASIC program. It is intended for inspection, comparison and documentation; use the `.8xp` file for installation.

For readability on GitHub, the line-by-line annotated version is split into six parts. Together they document every nonblank line of the v1.1 program listing:

1. [`docs/annotated/lines-001-100.md`](docs/annotated/lines-001-100.md)
2. [`docs/annotated/lines-101-200.md`](docs/annotated/lines-101-200.md)
3. [`docs/annotated/lines-201-300.md`](docs/annotated/lines-201-300.md)
4. [`docs/annotated/lines-301-401.md`](docs/annotated/lines-301-401.md)
5. [`docs/annotated/lines-402-501.md`](docs/annotated/lines-402-501.md)
6. [`docs/annotated/lines-502-577.md`](docs/annotated/lines-502-577.md)

The annotation explains the user-interface branches, input validation, Julian Date and ΔT handling, Meeus-style solar ephemeris plus the v1.1 eight-term longitude perturbation correction, Hc and Zn calculation, Bennett refraction, semidiameter, parallax, intercept calculation, the single-screen low-Sun, near-zenith and large-intercept cautions, and the error handlers.

**Do not paste the annotated files into TI Connect CE.** For installation, transfer `SUNSIGHT.8xp` with TI Connect CE.
