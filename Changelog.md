# picasso Changelog

# v2.7.1

- Further improvements to overall system stability and other minor adjustments have been made to enhance the user experience.

# v2.7

- Added `dst`, `litp` and `break` instructions (thanks to @Tilka).
- Added check to enforce index regs being used only with floating point vector uniforms.
- Renamed index registers to match D3D naming conventions (`a0.x`, `a0.y`, `aL`) (old names still accepted).
- Miscellaneous bugfixes and improvements (thanks to @lioncash).

# v2.6.2

- Fixed several compilation errors in some compilers.

# v2.6.1

- Reduced `mad` opdesc allocation errors by automatically swapping out of bounds opdesc entries with other ones in the addressable range (5 bits).

# v2.6

- Added `.in` directive for explicit specifying (and allocating) input registers and exporting them in the DVLE uniform table.
- Added support for dollar signs (`$`) in identifier names, which are translated to period characters (`.`) in DVLE uniform names.
- Output registers `o7` through `o15` are now allowed in vertex shaders (as dummy outputs).
- DVLE uniform table is now sorted by register position.

# v2.5

- The `.gsh` directive has been enhanced to provide full support for all geometry shader operation modes (point, variable-sized primitive and fixed-size primitive). This also effectively separates vertex shader uniform space from geometry shader uniform space.
- The `.out` directive has been enhanced to allow wiring semantics to any arbitrary output register. Additionally the `dummy` semantic was added while the `7` semantic was removed.
- Added auto-insertion of NOP instruction in corner cases involving flow of control instructions, together with the `--no-nop` directive which instead of adding NOPs warns the user about the corner cases.
- Added support for `rgba` and `stpq` in addition to `xyzw`.
- Added an error message for invalid input register use (e.g. `add r0, v1, v2`).
- The operand descriptor allocation algorithm has been enhanced to take into account unused operands.
- The `6` and `7` conditional operators have been removed since they actually do not exist.
- Really corrected MAD instruction encoding.
- Several miscellaneous issues were fixed.

# v2.4

- Corrected MAD instruction encoding.
- Added command line flag for retrieving the picasso version.

# v2.3

- Added `.constfa` for creating floating-point vector constant arrays.
- Fixed `.nodvle` bug.

# v2.2

- Added proper support for the MOVA instruction.
- Added support for inverting the condition in JMPU.
- Fixed `lcnt` bug.

# v2.1

- Fixed input file open error message.
- Fixed `.constf` misallocation bug.

# v2.0

- (**Breaking change**) Command line format changed.
- Added support for assembling multiple shaders (DVLEs) into a single SHBIN.
- Added new directives: `.entry`, `.nodvle`, `.gsh`, `.setf`, `.seti`, `.setb`.
- Added auto-detection of inverted forms of opcodes. (Explicitly using `dphi`, `sgei`, `slti` and `madi` is now deprecated)
- Several miscellaneous bug fixes.

# v1.0

- Initial release.
