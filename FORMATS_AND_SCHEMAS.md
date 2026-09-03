# 3D Formats & Metadata Schemas

Raw 3D assets are inherently messy. They come in varying scales, differing coordinate systems, and fragmented material definitions. For AI training and automated simulation pipelines, this inconsistency creates massive engineering bottlenecks.

At ObjectsXL, we engineer our datasets to eliminate these bottlenecks. This document outlines the 3D file formats we support and the standardized metadata schemas we apply to guarantee seamless pipeline integration.

## Supported File Formats

Our spatial data engine supports a wide array of industry-standard formats to ensure compatibility with your preferred data loaders, rendering engines, and simulation environments (such as NVIDIA Omniverse, Unity, Unreal Engine, and custom PyTorch/TensorFlow pipelines).

*   **Universal Scene Description (`.usd`, `.usda`, `.usdc`):** Our preferred format for complex, scalable simulation and digital twin environments.
*   **GL Transmission Format (`.gltf`, `.glb`):** Highly optimized, runtime-ready formats ideal for rapid loading and web-based spatial applications.
*   **Filmbox (`.fbx`):** Standardized format supporting complex geometry, skeletal hierarchies, and highly detailed motion capture data.
*   **Wavefront (`.obj`):** The universal standard for static geometry and straightforward point-cloud translation.
*   **Native Authoring Formats (`.blend`, `.duf`):** Provided where deep, non-destructive editing or character manipulation is required prior to dataset compilation.

## The ObjectsXL Metadata Schema

Every asset delivered by ObjectsXL is wrapped in a strict, JSON-based metadata schema. This ensures your data loaders can automatically parse, categorize, and utilize the assets without manual intervention.

Our standard schema guarantees the following structured data points:

### 1. Spatial & Geometric Data
*   **Real-World Scale:** All assets are normalized to real-world metric scales (e.g., 1 unit = 1 meter).
*   **Coordinate System:** Standardized Up-axis (Y-up or Z-up, defined in the dataset manifest) and handedness.
*   **Bounding Box Data:** Pre-calculated extents for collision detection and spatial indexing.
*   **Topology Metrics:** Polygon counts, vertex counts, and UV mapping status.

### 2. Semantic & Classification Tags
*   **Hierarchical Categorization:** Standardized taxonomy (e.g., `Vehicle > Wheeled > Commercial > Delivery Truck`).
*   **Material Properties:** Physically Based Rendering (PBR) mappings, including roughness, metalness, and albedo declarations.
*   **Dynamic Properties:** Identification of articulated parts, rig hierarchies, or morph targets.

### 3. Provenance & Compliance Tracking
*   **Unique Identifier (UUID):** A persistent ID tracking the asset back to its source studio.
*   **License Tier:** Machine-readable clearance flags ensuring the asset is authorized for the specific compute task running in your pipeline.

## Pipeline Integration

Because our assets adhere strictly to these formats and schemas, integrating ObjectsXL datasets into your AI workflow is straightforward. 

*(Note: As we expand this GitHub organization, we will release open-source Python validation scripts and PyTorch/TensorFlow data loader snippets designed to consume our metadata schemas natively.)*

---
*For technical support regarding our schemas or format integration, please open a Discussion in this repository or refer to our [SUPPORT.md](SUPPORT.md).*
