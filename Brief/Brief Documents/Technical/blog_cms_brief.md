# 🚢 Blog & CMS Development Brief - ReCrewables

## 📋 **Recommended Solution: Forestry CMS (Tina CMS)**

**Why This Solution:**
- ✅ **Free tier available** with generous limits
- ✅ **Separate login interface** for content management
- ✅ **Team collaboration** with role-based access
- ✅ **Git-based workflow** (content stored in your repository)
- ✅ **Perfect Next.js integration** with zero backend maintenance
- ✅ **Rich media support** for maritime images and videos
- ✅ **No development resources required** for setup

---

## 🎯 **Content Strategy**

### Monthly Content Types:
1. **Industry Insights** - Maritime technology trends and analysis
2. **Case Studies** - Real project deliveries and lessons learned  
3. **Technical Guides** - Vessel management and operational best practices
4. **Company Updates** - Project announcements and team achievements
5. **Guest Posts** - Industry experts and client perspectives

### Target Content Structure:
```
/blog/
├── industry-insights/
├── case-studies/
├── technical-guides/
├── company-updates/
└── guest-posts/
```

---

## 🛠 **Technical Implementation**

### 1. **Content Management Setup**
```javascript
// tina/config.ts - Tina CMS Configuration
import { defineConfig } from "tinacms"

export default defineConfig({
  branch: "main",
  clientId: process.env.NEXT_PUBLIC_TINA_CLIENT_ID,
  token: process.env.TINA_TOKEN,
  
  build: {
    outputFolder: "admin",
    publicFolder: "public",
  },
  
  media: {
    tina: {
      mediaRoot: "images/blog",
      publicFolder: "public",
    },
  },
  
  schema: {
    collections: [
      {
        name: "blog",
        label: "Blog Posts",
        path: "content/blog",
        format: "mdx",
        
        fields: [
          {
            type: "string",
            name: "title",
            label: "Title",
            required: true,
          },
          {
            type: "string",
            name: "excerpt",
            label: "Excerpt",
            required: true,
          },
          {
            type: "datetime",
            name: "publishedAt",
            label: "Published Date",
            required: true,
          },
          {
            type: "string",
            name: "author",
            label: "Author",
            required: true,
            options: [
              "Captain John Smith",
              "Sarah Williams - Technical Manager", 
              "Mike Johnson - Fleet Operations",
              "ReCrewables Team"
            ]
          },
          {
            type: "string",
            name: "category",
            label: "Category",
            required: true,
            options: [
              "Industry Insights",
              "Case Studies", 
              "Technical Guides",
              "Company Updates",
              "Guest Posts"
            ]
          },
          {
            type: "image",
            name: "featuredImage",
            label: "Featured Image",
            required: true,
          },
          {
            type: "string",
            name: "tags",
            label: "Tags",
            list: true,
          },
          {
            type: "rich-text",
            name: "body",
            label: "Content",
            isBody: true,
          },
        ],
      },
    ],
  },
})
```

### 2. **Blog Page Implementation**
```typescript
// app/blog/page.tsx - Enhanced Blog Listing
import { client } from "@/tina/__generated__/client"
import BlogCard from "@/components/blog/BlogCard"
import BlogHero from "@/components/blog/BlogHero"

export default async function BlogPage() {
  const { data } = await client.queries.blogConnection()
  const posts = data.blogConnection.edges?.map(edge => edge?.node) || []
  
  // Sort by publish date, most recent first
  const sortedPosts = posts.sort((a, b) => 
    new Date(b.publishedAt).getTime() - new Date(a.publishedAt).getTime()
  )
  
  const featuredPost = sortedPosts[0]
  const regularPosts = sortedPosts.slice(1)

  return (
    <main className="min-h-screen bg-brand-background">
      <Navigation />
      
      {/* Hero Section with Featured Post */}
      <BlogHero post={featuredPost} />
      
      {/* Blog Grid */}
      <section className="section-padding">
        <div className="section-container">
          <div className="max-w-6xl mx-auto">
            <h2 className="text-subheading text-white mb-12 text-center">
              Latest Maritime Insights
            </h2>
            
            <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
              {regularPosts.map((post, index) => (
                <BlogCard key={index} post={post} />
              ))}
            </div>
          </div>
        </div>
      </section>
      
      <Footer />
    </main>
  )
}
```

### 3. **Individual Blog Post Template**
```typescript
// app/blog/[slug]/page.tsx - Blog Post Page
import { client } from "@/tina/__generated__/client"
import { TinaMarkdown } from "tinacms/dist/rich-text"
import Image from "next/image"

export default async function BlogPost({ params }: { params: { slug: string } }) {
  const { data } = await client.queries.blog({
    relativePath: `${params.slug}.mdx`
  })
  
  const post = data.blog

  return (
    <main className="min-h-screen bg-brand-background">
      <Navigation />
      
      <article className="section-padding">
        <div className="section-container">
          <div className="max-w-4xl mx-auto">
            {/* Header */}
            <header className="mb-12">
              <h1 className="text-heading text-white mb-4">{post.title}</h1>
              
              <div className="flex flex-wrap items-center gap-4 mb-6 text-brand-foreground/80">
                <span>{post.author}</span>
                <span>•</span>
                <time>{new Date(post.publishedAt).toLocaleDateString()}</time>
                <span>•</span>
                <span className="bg-maritime-500/20 px-3 py-1 rounded-full text-sm">
                  {post.category}
                </span>
              </div>
              
              <p className="text-subtitle mb-8">{post.excerpt}</p>
              
              {/* Featured Image */}
              <div className="relative aspect-video rounded-2xl overflow-hidden mb-8">
                <Image
                  src={post.featuredImage}
                  alt={post.title}
                  fill
                  className="object-cover"
                  priority
                />
              </div>
            </header>
            
            {/* Content */}
            <div className="prose prose-invert prose-maritime max-w-none">
              <TinaMarkdown content={post.body} />
            </div>
            
            {/* Tags */}
            {post.tags && (
              <div className="mt-12 pt-8 border-t border-maritime-700/30">
                <h3 className="text-white font-semibold mb-4">Tags</h3>
                <div className="flex flex-wrap gap-2">
                  {post.tags.map((tag, index) => (
                    <span
                      key={index}
                      className="bg-maritime-500/20 text-maritime-300 px-3 py-1 rounded-full text-sm"
                    >
                      {tag}
                    </span>
                  ))}
                </div>
              </div>
            )}
          </div>
        </div>
      </article>
      
      <Footer />
    </main>
  )
}
```

---

## 🎨 **Component Library**

### Blog Card Component
```typescript
// components/blog/BlogCard.tsx
import Image from "next/image"
import Link from "next/link"

interface BlogCardProps {
  post: {
    title: string
    excerpt: string
    author: string
    publishedAt: string
    category: string
    featuredImage: string
    _sys: { filename: string }
  }
}

export default function BlogCard({ post }: BlogCardProps) {
  const slug = post._sys.filename.replace('.mdx', '')
  
  return (
    <Link href={`/blog/${slug}`} className="group">
      <article className="bg-maritime-900/40 backdrop-blur-sm border border-maritime-700/30 rounded-2xl overflow-hidden transition-all duration-300 hover:border-maritime-500/50 hover:bg-maritime-900/60">
        {/* Image */}
        <div className="relative aspect-video overflow-hidden">
          <Image
            src={post.featuredImage}
            alt={post.title}
            fill
            className="object-cover transition-transform duration-300 group-hover:scale-105"
          />
          <div className="absolute top-4 left-4">
            <span className="bg-maritime-500/90 backdrop-blur-sm text-white px-3 py-1 rounded-full text-sm font-medium">
              {post.category}
            </span>
          </div>
        </div>
        
        {/* Content */}
        <div className="p-6">
          <h3 className="text-xl font-semibold text-white mb-3 group-hover:text-maritime-300 transition-colors">
            {post.title}
          </h3>
          <p className="text-brand-foreground/80 mb-4 line-clamp-3">
            {post.excerpt}
          </p>
          
          <div className="flex items-center justify-between text-sm text-brand-foreground/60">
            <span>{post.author}</span>
            <time>{new Date(post.publishedAt).toLocaleDateString()}</time>
          </div>
        </div>
      </article>
    </Link>
  )
}
```

---

## 📱 **Content Creation Workflow**

### Team Access Levels:
1. **Admin** - Full content management, publish/unpublish
2. **Editor** - Create, edit, submit for review
3. **Contributor** - Create drafts, limited editing

### Publishing Process:
```
1. Team Member logs into Tina CMS admin panel
   ↓
2. Creates new blog post with rich editor
   ↓  
3. Uploads maritime images via drag-and-drop
   ↓
4. Saves as draft for review
   ↓
5. Admin reviews and publishes
   ↓
6. Content automatically appears on website
```

### CMS Admin Interface Access:
- **URL:** `https://yoursite.com/admin`
- **Authentication:** GitHub OAuth (team members)
- **Real-time preview** of content changes
- **Mobile-friendly** content editing

---

## 🚀 **SEO & Performance Features**

### Automatic SEO Generation:
```typescript
// Automatic meta tags for each blog post
export async function generateMetadata({ params }: { params: { slug: string } }) {
  const { data } = await client.queries.blog({
    relativePath: `${params.slug}.mdx`
  })
  
  return {
    title: `${data.blog.title} | ReCrewables Maritime Blog`,
    description: data.blog.excerpt,
    keywords: data.blog.tags?.join(', '),
    openGraph: {
      title: data.blog.title,
      description: data.blog.excerpt,
      images: [data.blog.featuredImage],
      type: 'article',
    },
  }
}
```

### Performance Optimizations:
- **Static generation** for all blog posts
- **Image optimization** with Next.js Image component
- **Lazy loading** for blog card images
- **RSS feed** generation for subscribers

---

## 📋 **Implementation Checklist**

### Setup Phase (Week 1):
- [ ] Create Tina CMS account and configure project
- [ ] Set up content schema for maritime blog posts
- [ ] Configure team member access and permissions
- [ ] Create initial content templates

### Development Phase (Week 2):
- [ ] Build blog listing page with category filtering
- [ ] Create dynamic blog post template with rich content
- [ ] Implement blog card components with maritime styling
- [ ] Add search functionality for maritime topics

### Content Phase (Week 3):
- [ ] Create content creation guidelines for team
- [ ] Write first 3 blog posts covering different categories
- [ ] Set up image optimization for maritime photography
- [ ] Configure SEO templates and meta descriptions

### Launch Phase (Week 4):
- [ ] Train team on CMS interface and workflow
- [ ] Set up analytics for blog performance tracking
- [ ] Create RSS feed and newsletter signup
- [ ] Launch with announcement to maritime network

---

## 💰 **Cost Breakdown**

### Tina CMS Free Tier:
- **Content:** Unlimited posts and pages
- **Team:** Up to 3 editors
- **Storage:** 1GB for images/media
- **Bandwidth:** Generous free limits

### Upgrade Path (If Needed Later):
- **Pro Plan:** $29/month for unlimited team members
- **Advanced media management** and workflow features

---

## 🎯 **Content Calendar Template**

### Monthly Content Plan:
- **Week 1:** Industry Insights (maritime technology trends)
- **Week 2:** Case Study (recent project delivery)
- **Week 3:** Technical Guide (operational best practices)  
- **Week 4:** Company Update (team achievements, new projects)

### Maritime Content Ideas:
1. "Evolution of CTV Operations in Offshore Wind"
2. "Newbuild Supervision: Lessons from the Zephyr Project"
3. "SMS Implementation: A Master's Perspective"
4. "Officer Placement Trends in Renewable Energy"
5. "Technology Adoption in Maritime Operations"

---

**This solution provides your team with a professional, collaborative blog platform that requires zero technical maintenance while delivering excellent performance and SEO benefits for your maritime consultancy.**