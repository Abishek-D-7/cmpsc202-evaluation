# Deliverable 2: Implementation and Evaluation

**Team:** Lynsey Arthur, Abishek Dhakal, Jayden Wilson, Sam  
**Date:** [TODO]  
**Status:** Template — replace every placeholder with actual implementation details and measured results.

## Problem and approach

We narrow an image of height $n$ and width $m$ by removing $k$ vertical seams. Each seam contains one pixel per row; consecutive columns differ by at most one. Pixel energy represents [TODO: exact measure of visual importance]. Lower-energy seams are preferred.

- **Baseline:** Recursively enumerate every valid seam, accumulate its energy, and retain a minimum-energy seam. The baseline does not reuse subproblem results.
- **Proposed algorithm:** For energy $E[r][c]$, set $D[0][c] = E[0][c]$ and $D[r][c] = E[r][c] + \min_p D[r-1][p]$, where $p$ ranges over valid adjacent predecessor columns. Start at the smallest minimum in the bottom row and follow stored predecessors upward.
- **Multiple removals:** Remove the selected seam while preserving each row’s remaining pixel order, then recompute energies on the updated image. Repeat until reaching `target_width`.
- **Scope of optimality:** Dynamic programming can find a minimum-energy seam for the current image under the chosen energy function. Repeating this choice does not by itself prove that the entire sequence of $k$ removals has minimum total cost; state any stronger claim only if it is established.

## Implementation

For an image of current width $w$, the proposed method takes [TODO] time per seam and uses [TODO] auxiliary space. **Auxiliary space** is extra working memory beyond the input and output; specify whether copies, energy tables, parent pointers, and output storage are included. The baseline takes [TODO] time and [TODO] auxiliary space, with assumptions stated. Give total costs for $k$ removals if analyzed, accounting for shrinking width and energy recomputation.

 [TODO: describe the representation actually used and, if investigated, the tradeoff or measurements. Do not claim an improvement without evidence.]

## Testing

[TODO: add meaningful cases, image handling checks, and any known limitations.]

## Benchmark method

[TODO: describe the benchmark script, input generation, and measured data. Include hardware and software environment, number of repetitions, and any timeouts or limits.]

## Findings and limitations

[TODO: summarize the observed scaling and comparison using the measured data. Explain any timeouts, variation, and limits of the experiment. Include a visual observation of the output if tested; low-energy removal may still distort important structures or retain high-contrast static.]

## Contributions

- Abishek Dhakal, Lynsey Arthur, Jayden Wilson, Sam
