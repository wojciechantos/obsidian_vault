A technique introduced by Next.js that combines the benefits of static site generation (SSG) with dynamic content updates. It allows to pre-render static pages at build time while also enabling them to be updated at runtime without requiring a full rebuild.


**How it works?**
It allows to specify which pages should be statically generated at build time and which pages should be revalidated and regenerated in the background when requested by a user.
When a user requests a page that is set up for ISR, Next.js serves the statically generated version of the page while simultaneously initiating a background process to regenerate the page with fresh data. Once the regeneration is complete, the new vesion of the page is swapped in with seamless update to the user.


**Example**

```
import { useRouter } from 'next/router';
import { getPostBySlug } from '../../lib/posts';

export default function Post({ post }) {
	const router = useRouter();

	if(router.isFallback) {
		return <div>Loading...</div>;
	}

	return (
		<div>
			<h1>{post.title}</h1>
			<p>{post.content}</p>
		</div>
	);
}

export async function getStaticPaths() {
	return {
		paths: [],
		fallback: true,
	}
}

export async function getStaticProps({ params }) {
	const post = await getPostBySlug(params.slug);
	
	return {
		props: {
			post,
		},
		revalidate: 60 //Re-generate page every 60 seconds
	};
}

```