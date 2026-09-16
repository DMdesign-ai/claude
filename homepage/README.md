# Homepage hero badge (staging copy)

The TWINT staff badge for the hero of dragosmuntean.github.io. Kept here
because this session could not push to that repository.

`homepage-hero-badge.patch` holds both commits. From the root of a
`dragosmuntean.github.io` checkout:

```
git checkout -b hero-badge
git am path/to/homepage-hero-badge.patch
```

The three `.astro` files are the same change as plain files, for reference:
`HeroBadge.astro` and `HeroPhoto.astro` go in `src/components/race/`,
`index.astro` in `src/pages/`. The portrait goes in
`public/images/portrait/dragos.webp`.
