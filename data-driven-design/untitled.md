# Untitled

## ACID really just AID

<table>
  <thead>
    <tr>
      <th style="text-align:left">Title</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Atomic</td>
      <td style="text-align:left">If a transaction breaks half way, all partial changes will be reverted.</td>
    </tr>
    <tr>
      <td style="text-align:left">Consistency</td>
      <td style="text-align:left">
        <p>Shouldn&apos;t really belong; it is a property of the designed transaction.
          <br
          />AID are properties of the database.</p>
        <p>Basically same as program(transaction) invariant is maintained before
          and after if the program(transaction) is written correctly.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Isolation</td>
      <td style="text-align:left">
        <p>Concurrent access to same resource doesn&apos;t create race condition.</p>
        <p>Serialization is ideal isolation but rarely used due to performance.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Durability</td>
      <td style="text-align:left">
        <p>Literally means data that is committed doesn&apos;t get wiped out by physical
          electronic failure.</p>
        <p>Replication provides best durability , database must wait until replication
          completes before transaction is successful.</p>
      </td>
    </tr>
  </tbody>
</table>

