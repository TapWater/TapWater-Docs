# Activity Table

| Activity                  | Task | Task Precedence | Time (Weeks) |
|:--------------------------|:-----|:----------------|:-------------|
| Initialization            | A    | none            | .5           |
| __Server__                                                        |
| Database/Model Layer      | B    | A               | .5           |
| Authentication            | C    | B               | 1            |
| Mobile API Implementation | D    | C               | 1            |
| Views/View Controllers    | E    | A               | 2            |
| __iPhone App__                                                    |
| Core Data Setup           | F    | A               | .5           |
| Views/Controllers         | G    | A               | 1            |
| Drink Notifications       | H    | F, G            | 1            |
| Integration With Server   | I    | C, F            | .5           |
| User Authentication       | J    | I               | 1            |
| Synchronization           | K    | J               | 1            |