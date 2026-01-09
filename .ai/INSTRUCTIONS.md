# Recolo Project - AI Development Instructions

## Testing Protocol (MANDATORY)

Before marking any task as complete, you MUST:

### 1. Build Verification
```bash
npm run build
```
- Ensure build completes successfully
- Check for any TypeScript errors
- Verify no missing assets

### 2. Type Checking
```bash
npx astro check
```
- Run Astro's type checker
- Fix any type errors before proceeding

### 3. Live Testing
```bash
# Start dev server if not running
npm run dev

# Test each page loads without errors
curl -s -o /dev/null -w "%{http_code}" http://localhost:4321/
curl -s -o /dev/null -w "%{http_code}" http://localhost:4321/italian
curl -s -o /dev/null -w "%{http_code}" http://localhost:4321/vietnamese
```

Expected: All should return `200`

### 4. Component-Level Checks
- Verify all Astro components have proper frontmatter (`---` ... `---`)
- Check for unclosed tags
- Ensure imports are correct
- Validate CSS syntax

### 5. Browser Verification (When Possible)
- Open http://localhost:4321 in browser
- Check console for errors
- Test interactive elements
- Verify responsive design (use DevTools device emulation)

## Change Validation Checklist

Before telling user "it's done", verify:
- [ ] Build succeeds (`npm run build`)
- [ ] Type check passes (`npx astro check`)
- [ ] All pages return HTTP 200
- [ ] No console errors in browser
- [ ] Interactive elements work (forms, links, buttons)
- [ ] Images load correctly
- [ ] No broken styling

## Common Issues to Watch For

1. **Astro Frontmatter**: All `.astro` files need `---` ... `---` fences
2. **Image URLs**: Verify Unsplash URLs are valid and images load
3. **CSS Variables**: Ensure all custom properties are defined in `global.css`
4. **Responsive Design**: Test mobile viewport (375px width minimum)
5. **Cross-Origin Issues**: External images should work, but test them

## Deployment Checklist

Before deploying:
- [ ] All tests pass
- [ ] Environment variables set (if any)
- [ ] Production build successful
- [ ] No console errors
- [ ] Performance acceptable (Lighthouse score > 90)

## Post-Deployment Verification

After deploying to Vercel:
- [ ] Visit production URL
- [ ] Test all pages load
- [ ] Check mobile responsiveness
- [ ] Verify images load
- [ ] Test contact form
- [ ] Check page load times (< 3s)

## Remember
**Users see broken sites immediately. Test before claiming "it's done".**
