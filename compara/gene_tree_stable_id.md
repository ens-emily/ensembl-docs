# GeneTree stable IDs

We provide stable IDs for gene trees. The IDs are kept from one release to the other depending on the genes present in the Gene Tree. In particular, we do not rely on the underlying alignment, the tree structure or the resulting homologues to assign stable IDs to GeneTrees.

## Format

The format of the stable IDs is **ENSGTRRRRXXXXXXXXXX**:
* **ENSGT** Indicates that this is an Ensembl gene tree ID.
* **RRRR** corresponds to the Ensembl release number when the stable ID was first assigned.
* **XXXXXXXXXX** is a unique number.

For instance, ENSGT00560000077204 is a gene tree first described in Ensembl 56.

## Stable ID mapping

This is a generic description of the stable ID mapping algorithm. We use it to track stable IDs from release to release, but we also use it to match Ensembl gene trees to TreeFam entries.

The algorithm compares gene trees from the current release (old) to the gene trees from the forthcoming one (new). It is assumed that the new trees and old trees will tend to group proteins similarly. It does compares the proteins in the two trees using the Ensembl translation stable IDs.

When we compare old and new trees, there are three kinds of proteins:
1. SHARED (the ones present in both trees).
2. DISAPPEARING members (the ones present only in the old tree) - eg gene predictions or complete genomes that disappear in the next release.
3. NEWBORN members (the ones present only in the new tree) - eg new gene predictions or new complete genomes in the next release

The relationship between trees is inferred from the SHARED members, but the other two kinds are also counted by the algorithm.

The algorithm iterates through the new trees in the descending order of their sizes, trying to reuse the ID of one of the old trees from where the SHARED members come. When an ID is found that has not yet been used, it is assigned to the new class.

If 100% SHARED members of the old tree become 100% SHARED members of the new tree, we call this case an EXACT reuse. If there was only one SHARED member, we call it an EXACT_o for "orphan".

Otherwise we have a split/join situation and iterate through the "contributors" (the "old" classes from which the SHARED members come from) in the decreasing order of the sizes of the shared parts. This ordering ensures that both in cases of joins and splits we are reusing the name of the biggest contributor.

If the "old" class name of the first (the biggest) part has not yet been taken, we take it and call this a MAJORITY reuse. Due to the ordering (and looking at the statistics) this type of name reuse usually means that the SHARED majority of the biggest "old" contributor becomes the SHARED majority of the "new" class. If there was only one SHARED member, we call it an MAJORITY_o for "orphan", although this will rarely happen.
If the "old" class name of the first part has been taken, but one of the other "old" class names is still available, we take it and call it a NEXTBEST name. (these classes are usually very small, because the majority of the SHARED members participate in EXACT/MAJORITY cases).
If a name could not have been reused, because all the "old" contributor's names have been used, a completely new name is generated and it is a NEWNAME case. This usually means we are dealing with a split of a big class, where the majority has gone into an MAJORITY, and the rest of it needs a new name. Again, if there was only one SHARED member, we call it NEWNAME_o.
Finally, if we have a "new" class that only contains NEWBORN members (meaning there were no "old" classes to reuse the names from), a new name is also generated, but this is a NEWFAM case. If the new class has only one (NEWBORN) member, it is a NEWFAM_o case.
In this example diagram:

![Stable ID mapping}(http://www.ensembl.org/info/genome/compara/compara_stable_id_mapping.png "Stable ID mapping")

D1 is an EXACT reuse (cyan contributor)
A2 inherits the name from A1 according to the MAJORITY rule (light red contributor)
B2 inherits the name from B1 (pink contributor), and C1 name disappears in the new classification and it is merged into B2 (light green).
Z1 is created from NEWBORN members
Y1 is an example of NEWNAME (yellow contributor)

## Versioning

A version increase indicates that the SHARED members have changed for that class. The version is kept the same if it is an EXACT reuse case. For example, in the GeneTrees:

a) If a genetree with 50 members in release 56 turns into a genetree with 49+2 members in release 57, 49 being SHARED and 2 being NEWBORN, the version will change.

b) If a genetree with 50 members in release 56 turns into a genetree with 48+2 members in release 57, 48 being SHARED and 2 being NEWBORN, the version will change, even though the total number of members is the same.

c) If a genetree with 48+2 members in release 56 turns into a genetree with 48 members in release 57, 48 being SHARED and 2 being DISAPPEARING (e.g. updated genebuild that deletes some members), the version will be the same.

d) If a genetree with 48+2 members in release 56 turns into a genetree with 48+3 members in release 57, 48 being SHARED, 2 being DISAPPEARING and 3 being NEWBORN, the version will be the same.
