# Pitch classes library

A library for working with pitch class sets and interval sets. A pitch class is a list of MIDI note values from the first octave (0-11) to which other pitches can be compared using modulo 12. 0 = C, 1 = C#, and so on. To use these functions, you need to send `(sys:load "libs/core/pc_ivl.xtm")` to the extempore session.

## Working with scales

A scale can be defined as a pitch class. One way to do this is the pc:scale function, which returns a scale of a given type based on a supplied root:

    (define *c-major* (pc:scale 0 'ionian))
    -> (0 2 4 5 7 9 11)

    (define *a-aeolian* (pc:scale 9 'aeolian))
    -> (9 11 0 2 4 5 7)

A scale can also be derived from a chord:

    (define *c-minor* (pc:scale-from-chord 0 '(0 3 7)))
    -> (0 2 3 5 7 8 10)
