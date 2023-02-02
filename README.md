# WNBATeamsLibrary


getArenaAndCapacity(teamNameInput) uses the input of a team name (teamNameInput{string}) and returns the team's home arena and its capacity

getTeamsInConference uses the input of a conference name (confrence{string}) and returns the names of the teams in the confrence

getCoach(team) uses the input of a team name (team{string}) and returns the name of the head coach

getTotalCapacityOfTeams(teamListInput) uses a list of inputed teams (teamListInput{list}) and returns the total capacity of the arenas of the teams in the list

getArenaByCity(cityInput) uses an inputed city (cityInput{string}) to return the name of the Arena in that city

CODE START


var url = "https://raw.githubusercontent.com/b-mcavoy/datasets/main/Sports/WNBA%20Teams.csv";

var conferences = getColumn(url, 1);
var teams = getColumn(url, 2);
var cities = getColumn(url, 3);
var arenas = getColumn(url, 4);
 var capacities = getColumn(url, 5);
var teamJoined = getColumn(url, 6);
var headCoach = getColumn(url, 7)
console.log(cities);


function getArenaAndCapacity(teamNameInput){
  var output = [];
  for(var i = 0; i < teams.length; i++){
    if(teams[i].toLowerCase().includes(teamNameInput.toLowerCase())){
      output.push(arenas[i])
      output.push(capacities[i])
    }
  }if(output.length == 0){
    return "Input Not Valid"
}else{
  return output;
}
}


  function getTeamsInConference(conference) {
  var teamsInConference = [];
  for (var i = 0; i < teams.length; i++) {
    if (conferences[i].toLowerCase().includes(conference.toLowerCase())) {
      teamsInConference.push(teams[i])
    }
  }if(teamsInConference.length == 0){
   return "Input Not Valid"
}else{
  return teamsInConference;
  }
}


function getCoach(team) {
  var headCoachByTeam = [];
for (var i = 0; i < teams.length; i++) {
  if (teams[i].toLowerCase().includes(team.toLowerCase())){
  }
}if(headCoachByTeam.length == 0){
  return "Input Not Valid"
}else{
return headCoachByTeam
}
}


function getTotalCapacityOfTeams(teamListInput){
  var totalCapacity = 0;
  for(i = 0; i < teams.length; i++){
    if(teamListInput.includes(teams[i])){
      totalCapacity = totalCapacity + parseInt(capacities[i])
    }
  }if(totalCapacity == 0){
    return "Input Not Valid"
  }else{
    return totalCapacity
  }
}


function getArenaByCity(cityInput){
  var arena = "";
  for(var i = 0; i < teams.length; i++){
    if(cities[i].toLowerCase().includes(cityInput.toLowerCase())){
      arena = arenas[i]
    }
  }if(arena == ""){
    return "Input Not Valid"
  }
  return arena
}
