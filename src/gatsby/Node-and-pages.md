---
name: Nodes and Pages
menu: Gatsby
route: gatsby/node-and-pages
---

# Node and Pages

## create node and create page programatically

```js
const path = require(`path`)
const { createFilePath } = require(`gatsby-source-filesystem`);

exports.onCreateNode = ({ node, getNode, actions }) => {
    const { createNodeField } = actions;
    if (node.internal.type === `MarkdownRemark`) {
        const fileNode = getNode(node.parent)
        const slug = createFilePath({ node, getNode, basePath: `pages` })
        createNodeField({
            node,
            name: `slug`,
            value: slug,
        })
    }
};
exports.createPages = async ({ graphql, actions }) => {
    const { createPage } = actions;
    // **Note:** The graphql function call returns a Promise
    // see: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise for more info
    const result = await graphql(`
    query {
      allMarkdownRemark {
        edges {
          node {
            fields {
              slug
            }
          }
        }
      }
    }
  `);
    result.data.allMarkdownRemark.edges.forEach(({node}) => {
        createPage({
            path: node.fields.slug,
            component: path.resolve(`./src/templates/blog-post.js`),
            context: {
                // Data passed to context is available
                // in page queries as GraphQL variables.
                slug: node.fields.slug,
            },
        });
    });
}

```

The above code do
-   add node field `slug` into node `MarkdownRemark.edges.node`
-   make graphQL to find out all the slug available and create pages using that slug, using template at `./src/templates/blog-post.js`, and it passed 1 variable `slug` into that template