# Inverse forming of auricular components

18 September 2026 · exploratory development model

## Clinical evidence and the question being tested

Keeping every non-helical component rigid was a modeling choice, not a universal rule of surgery. Wang et al. describe reorienting seventh-cartilage remnant stock for the tragus and bending the antihelix to form an antitragus that is secured to the base. This supports explicitly separating a carved starting shape from its assembled configuration. It does not establish permissible arbitrary folds or twists, a strain limit, or mechanical suitability of older cadaveric grafts. [Wang et al., 2025](https://journals.sagepub.com/doi/10.1089/fpsam.2024.0154).

Gandy et al. demonstrated modular assembly from thin porcine cartilage slices in an ex vivo study. Their use of electromechanical reshaping for part of the helix is distinct from passive elastic bending. It is not implemented here and cannot be treated as evidence that an elastically bent human graft retains a permanent shape. [Gandy et al., 2016](https://pmc.ncbi.nlm.nih.gov/articles/PMC4968401/).

The supplied dissection handbook continues to define component roles and assembly concepts. The attachment coordinates in this experiment are automatically proposed from nearby framework surfaces; they are **not recovered handbook landmarks or surgeon-approved stitch positions**.

## The two problems remain separate

1. Find a starting solid that is completely contained in native cartilage with the retained 0.8 mm research margin.
2. Compute how that solid approaches the unchanged ear component under shaping guides and then under tension-only stitches, reporting shape error, strain, force and convergence.

A cut-stock certificate does not certify forming, fixation, tissue integrity, minimum thickness, machining access or the complete assembled framework. Components are not jointly allocated in this experiment. Inter-component collisions and deformation of supporting pieces are not resolved.

## Kinematics and material law

The 58.9 mm reference and existing component surfaces are preserved. Long target triangles are subdivided without changing their surface. Each component receives four dimensionless shape coordinates: two cylindrical bends, a twist and a rounded-fold shear. Search also optimizes three rigid rotations and three translations.

For a bend in coordinates u,w with curvature k, let s = sqrt(1 + 2kw). The map is u′ = s sin(ku)/k, w′ = [s cos(ku) − 1]/k, with its continuous identity limit at k = 0. It has determinant one. The rounded fold is w′ = w + a h(u), where h(u) = 6 log cosh(u/6); its transverse shear is included in the material strain. It is not a cut, scored hinge or free rotation. Twist rotates the two transverse coordinates by an angle proportional to the longitudinal coordinate and also has determinant one.

A propagated bounding-box check requires positive bend radius and an angular interval shorter than π for each cylindrical bend. The shear and twist have explicit global inverses. This prevents the continuous mapping from introducing self-crossing. It does not replace contact analysis between different components or validate the original draft architecture. Exported surfaces remain piecewise-linear approximations to the continuous mapping.

The carved starting configuration is assumed stress-free. At a material point, the forming gradient is F = J(current) J(start)⁻¹. Elastic energy is an incompressible neo-Hookean scenario, W = μ[tr(FᵀF) − 3]/2, integrated with regular interior quadrature normalized to the original solid volume. Here μ = E/[2(1 + ν)], using E = 8.8 MPa and ν = 0.45. The restricted deformation family has det(F) = 1, so volume is imposed kinematically. It is not a free-node finite-element solution; unavailable modes can make it overly restrictive. The bending map restricts lateral relaxation and does not reproduce an unconstrained beam in every loading condition.

The E scenario comes from Grellmann et al.'s reported human costal-cartilage flexural modulus, with 5.9 and 11.7 MPa used as sensitivity scenarios. Converting this to an isotropic shear response is an engineering assumption, not a measured torsion or multiaxial calibration. [Grellmann et al., 2006](https://onlinelibrary.wiley.com/doi/10.1002/jbm.a.30625).

Goh and Anderson found nonlinear loading/unloading behavior and substantial variation in intact cadaveric ribs with retained perichondrium. Their approximately 5% nominal test-strain range is not a permissible-strain or fracture threshold for these carved components. The nonlinear coefficients from their beam experiment are not transplanted into an uncalibrated three-dimensional constitutive law here. The present simple law cannot represent their loading/unloading response. [Goh and Anderson, 2025](https://pmc.ncbi.nlm.nih.gov/articles/PMC11653008/).

The 5%, 10% and 20% screens refer to maximum **sampled principal logarithmic strain**, considering both extension and compression. They are analyst-selected sensitivity levels, not safety limits. Surface vertices and volume points are checked; this is not a continuum-wide strain certificate. Calcification, anisotropy, cutting-induced residual stress, damage, relaxation and permanent set remain absent. No stitch pull-out or failure load is asserted.

## Search and fair comparison

The ten verified G3 adult cases are used as development examples. Other CCSeg cases are not relabeled adult. Each case/component starts from the two most promising previously searched expanded-inventory domains. Rigid control and flexible searches have the same placement seeds, native masks and boundary margin. The initial Powell search permits up to 2,400 evaluations per start. Near failures with original search loss ≤4 receive two additional active-surface rounds, each allowing up to 1,200 evaluations, using exact distances to background voxel cuboids.

The sparse optimization only proposes a pose. Candidate deformation is tightened against all target vertices and volume points, then the complete mapped solid must pass the independent adaptive native-mask cover. Mesh volume must agree with the target within 0.5%. No tissue is added between labels. Existing rigid cuts are retained at every wider strain screen. A numerically undeformed cut discovered in a flexible run is classified as rigid, not credited as a bending gain.

This bounded four-mode search has not added any verified case/component cut beyond the updated rigid control. Updated adult counts are base 0/10, antihelix 3/10 and tragal complex 7/10; the previous rigid study had 0, 0 and 6 respectively. The improvement is attributable to additional placement search. Failed examples remain visible as **unverified starting cuts** in the forming demonstration. This is neither proof that bending cannot help nor evidence that these current component shapes are surgically appropriate.

## Guides, sutures and release

Twelve material points are chosen from portions of each component near the other target components, spread across the available surface. Their anchors are nearest vertices on those neighboring targets, which remain fixed. The helix support uses the current 1.5 × 2.7 mm target strip. These are proposed links, not validated fixation sites.

Temporary guides are three-axis springs with assumed stiffness 5 N/mm. They move through five configurations toward the unchanged target. Then tension-only cables are engaged: their energy is k max(distance − length, 0)²/2, with assumed k = 1 N/mm. Their lengths are 90% of the target gaps, bounded below by 0.05 mm; this is an explicit preload scenario, not a surgical recommendation. Guide stiffness is reduced through 1, 0.1 and 0 N/mm. The solver optimizes the four shape modes plus each component's rigid pose, with fixed neighboring supports.

Removing every support returns the purely elastic model to its assumed rest shape. Its rigid display position is arbitrary, and the sequence has no time scale. No claim is made about real recovery speed or permanent shaping. Shape error is the RMS difference between corresponding component vertices and the fixed target, with no best-fit registration that could conceal displacement. Individual stitch tension is distinct from guide force.

## Verification and next extension

Analytical checks cover determinant-one maps, independently differentiated gradients, injective-domain rejection, small-curvature beam energy, zero rest energy, material scaling, and tension-only cable behavior. Report checks retain input hashes, unchanged target dimensions, complete cut certificates, export topology, a finer volume integration grid, solver residuals and material sensitivity.

The next useful extension is independently controlled branch bending and a shell or solid finite-element model with coupled contacts and attachment reactions. It should follow reviewed component boundaries and physical bending/attachment measurements. Expanding the parameter count alone would not establish that additional geometric fits are mechanically usable.
