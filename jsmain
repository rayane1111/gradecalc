let assignments = [];

function addAssignment() {
  const name = document.getElementById('assignmentName').value;
  const score = parseFloat(document.getElementById('score').value);
  const weight = parseFloat(document.getElementById('weight').value);

  if (!name || isNaN(score) || isNaN(weight)) {
    alert("Please fill out all fields.");
    return;
  }

  assignments.push({ name, score, weight });
  updateTable();
  clearInputs();
}

function updateTable() {
  const tbody = document.querySelector("#assignmentTable tbody");
  tbody.innerHTML = "";
  assignments.forEach(a => {
    const row = `<tr>
      <td>${a.name}</td>
      <td>${a.score}%</td>
      <td>${a.weight}%</td>
    </tr>`;
    tbody.innerHTML += row;
  });
}

function clearInputs() {
  document.getElementById('assignmentName').value = '';
  document.getElementById('score').value = '';
  document.getElementById('weight').value = '';
}

function calculateFinal() {
  let totalWeighted = 0;
  let totalWeight = 0;

  assignments.forEach(a => {
    totalWeighted += a.score * a.weight;
    totalWeight += a.weight;
  });

  const result = totalWeight === 0 ? 0 : (totalWeighted / totalWeight).toFixed(2);
  document.getElementById('resultText').innerText = `📘 Your current grade is: ${result}%`;
}

function resetAll() {
  assignments = [];
  updateTable();
  document.getElementById('resultText').innerText = "Your final grade will appear here.";
}
