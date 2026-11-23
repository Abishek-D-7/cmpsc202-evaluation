# Deliverable 2: Seam Carving Implementation and Evaluation

Build a prototype that narrows an image by repeatedly removing a low-energy vertical seam. A seam contains one pixel per row, and consecutive columns differ by at most one. Compare the baseline and proposed dynamic programming algorithm under the same energy definition and inputs. The baseline exhaustively enumerates seams and the proposed method uses dynamic programming. Both recalculate energy after each removal and use the same tie rule.
