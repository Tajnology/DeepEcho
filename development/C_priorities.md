# Priorities
Relative priorities:
- Play the value on the master bus at an interval
- Check inputs
- Handle input interrupts
- Update indicators
- Process the block in the sum bus
- Process the blocks in each of the voices

Order of operations:
- Play the value on the master bus
- Check inputs
- Update indicators
    - Pull blocks for any voice that has less than 2 * MIN blocks available
    - Process any sample that has less than 2 blocks in its output
    - 