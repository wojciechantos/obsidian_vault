The RSC Payload is a compact binary representation of the rendered React Server Component tree. It's used by React on the client to update the browser's DOM. The RSC payload contains:
- The rendered result of Server Components
- Placeholders for where Client Components should be rendered and references to their JS files
- Any props passed from a Server Component to a Client Component

