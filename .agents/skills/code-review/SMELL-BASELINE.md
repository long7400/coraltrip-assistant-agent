# Smell Baseline

Use this Fowler-inspired baseline for the Standards axis when repo standards do not override it. These are judgement calls, not hard violations; skip what tooling already enforces.

- **Mysterious Name** - a function, variable, or type name does not reveal what it does or holds. Fix by renaming; if no honest name exists, the design is murky.
- **Duplicated Code** - the same logic shape appears in more than one hunk or file. Extract the shared shape and call it from both.
- **Feature Envy** - a method reaches into another object's data more than its own. Move the behavior toward the data it envies.
- **Data Clumps** - the same fields or params keep travelling together. Bundle them into one type.
- **Primitive Obsession** - a primitive or string stands in for a domain concept. Give the concept a small type.
- **Repeated Switches** - the same switch/if cascade on the same type recurs. Replace with polymorphism or one shared map.
- **Shotgun Surgery** - one logical change forces scattered edits. Gather what changes together into one module.
- **Divergent Change** - one file or module is edited for unrelated reasons. Split so each module changes for one reason.
- **Speculative Generality** - abstraction, parameters, or hooks were added for needs the spec does not have. Delete or inline until a real need appears.
- **Message Chains** - callers navigate through long object chains. Hide the walk behind one method on the first object.
- **Middle Man** - a class or function mostly delegates onward. Remove it and call the real target.
- **Refused Bequest** - a subclass or implementer ignores most inherited behavior. Drop inheritance and use composition.
