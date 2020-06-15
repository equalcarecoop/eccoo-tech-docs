---
description: This page outlines critical architecture decisions that have been made
---

# architecture decisions

<table>
  <thead>
    <tr>
      <th style="text-align:left">Decision</th>
      <th style="text-align:left">Options</th>
      <th style="text-align:left">Rationale</th>
      <th style="text-align:left">Implications</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Use a graph database to underpin the social network aspects</td>
      <td style="text-align:left">
        <ul>
          <li>Graph DB</li>
          <li>NoSQL DB</li>
          <li>SQL DB</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Simple to model social graph with Graph Database</li>
          <li>Edges (links between Nodes) are first class entities</li>
        </ul>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Use a GraphQL protocol layer</td>
      <td style="text-align:left">
        <ul>
          <li>GraphQL</li>
          <li>REST</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>GraphQL domain schema provides consistent language</li>
          <li>RESTful APIs can be more difficult to maintain consistency</li>
          <li>GraphQL can be more efficient on network due to less over or under requesting</li>
          <li>Can create custom queries for each activity</li>
          <li><a href="https://www.howtographql.com/basics/1-graphql-is-the-better-rest/">https://www.howtographql.com/basics/1-graphql-is-the-better-rest/</a>
          </li>
        </ul>
      </td>
      <td style="text-align:left">Will need to train dev team in GraphQL</td>
    </tr>
    <tr>
      <td style="text-align:left">Vue.js as a front-end SPA framework</td>
      <td style="text-align:left">
        <ul>
          <li>React</li>
          <li>Vue</li>
          <li>Angular</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Vue/Vuex architecture is very clean, particularly the .vue single file</li>
        </ul>
      </td>
      <td style="text-align:left">Need to ensure Dev team on board with this</td>
    </tr>
    <tr>
      <td style="text-align:left">(PENDING: Data store for transactions)</td>
      <td style="text-align:left">
        <ul>
          <li>Blockchain</li>
          <li>Other Ledger Database</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Need for non-repudiability</li>
          <li>Blockchain underpins distributed trust</li>
        </ul>
      </td>
      <td style="text-align:left">May be overkill. Dev training.</td>
    </tr>
  </tbody>
</table>

