# Companion Stage

A photoreal 3D companion running in the browser: three.js r186, a Daz Genesis
rig with 183 bones, soft-tissue simulation, and six behaviour blocks — face,
gaze, hair, torso roll, balance and mood.

Vertical by design. It is built to be held in one hand.

## What is here

    index.html    the viewer: scene, materials, lighting, panel, clip rail,
                  arm grab and the soft-tissue system
    js/           six generated behaviour blocks, wrapped verbatim from their
                  owning source files — do not edit these by hand
    _t/           three.js r0.186.0, vendored, so the site has no CDN dependency
    *.wasm        glTF binary buffers (geometry and animation)
    *.json        the two glTF manifests
    *.webp        textures

Everything is static. There is no build step: Netlify publishes the directory
as it stands.

## Regenerating it

This directory is assembled from the source repo, which holds the Blender
pipeline, the probes and the notes:

    python3 pipeline/build_site.py --worktree

That wraps the viewer in a real HTML document, points the importmap at the
vendored three.js instead of the CDN, and copies the blocks and assets flat.

## The character

269,932 triangles, 196,201 vertices, 183 bones (176 stock plus seven
soft-tissue), 61 of them facial. No shape keys — every expression is bone-driven.
