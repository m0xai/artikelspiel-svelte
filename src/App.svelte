<script>
  import Frage from './Frage.svelte';
  import Punkte from './Punkte.svelte';
  import Antworten from './Antworten.svelte';

  let insFrage = 0;
  let plusPunkt = 0;
  let minusPunkt = 0;
  const fragen = [
    { frage: 'Ärger', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Abend', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Abflug', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Absender', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Alkohol', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Anfang', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Angestellte',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Anruf', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Anrufbeantworter',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    {
      frage: 'Anschluss',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Anzug', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Apfel', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Appetit', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'April', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Arbeitsplatz',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Arm', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Arzt', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Aufenthalt',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Aufzug', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'August', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Ausflug', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Ausgang', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Ausländer',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Ausweis', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Automat', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Bahnhof', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Bahnsteig',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Balkon', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Baum', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Beamte', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Bekannte', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Berg', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Beruf', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Besuch', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Betrag', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Bildschirm',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    {
      frage: 'Bleistift',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Blick', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Bogen', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Brief', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Briefkasten',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    {
      frage: 'Briefumschlag',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Bruder', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Buchstabe',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Bus', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Chef', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Computer', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Dank', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Deutsche', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Dezember', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Dienstag', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Doktor', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Dom', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Donnerstag',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Drucker', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Durst', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Ehemann', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Eingang', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Eintritt', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Einwohner',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    {
      frage: 'Empfänger',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Empfang', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Enkel', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Erwachsene',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Export', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Führerschein',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Fahrer', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Fahrplan', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Familienname',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    {
      frage: 'Familienstand',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Februar', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Fehler', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Film', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Fisch', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Flughafen',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Flur', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Fluss', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Fotoapparat',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Frühling', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Freitag', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Freund', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Friseur', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Fuß', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Fußball', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Garten', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Gast', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Geburtsort',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    {
      frage: 'Geburtstag',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    {
      frage: 'Glückwunsch',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    {
      frage: 'Großvater',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Gruß', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Hals', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Haushalt', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Hausmann', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Herbst', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Herd', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Herr', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Hund', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Hunger', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Import', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Inhalt', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Januar', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Job', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Jugendliche',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Juli', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Junge', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Juni', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Käse', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Körper', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Kühlschrank',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Kaffee', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Kalender', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Kassettenrecorder',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Keller', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Kellner', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Kindergarten',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    {
      frage: 'Kinderwagen',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Kiosk', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Koffer', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Kollege', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Kontakt', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Kopf', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Kredit', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Kreis', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Kuchen', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Kugelschreiber',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Kunde', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Kurs', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Löffel', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Laden', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Lehrer', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'LKW', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Loch', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Lohn', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'März', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Müll', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Magen', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Mai', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Mann', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Mantel', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Markt', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Mechaniker',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Mensch', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Messer', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Mittag', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Mittwoch', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Moment', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Monat', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Montag', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Morgen', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Motor', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Mund', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Nachbar', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Nachmittag',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Name', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Nebel', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Norden', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Notarzt', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Notfall', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'November', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Ober', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Oktober', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Opa', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Ort', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Osten', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Park', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Partner', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Pass', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Pkw', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Plan', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Platz', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Preis', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Prospekt', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Pullover', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Rücken', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Rabatt', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Raucher', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Raum', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Regen', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Reifen', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Reis', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Reiseführer',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Rock', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Rosé', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Rundgang', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Süden', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Saft', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Salat', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Satz', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Schüler', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Schalter', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Schild', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Schinken', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Schirm', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Schlüssel',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Schluss', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Schnee', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Schnupfen',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Schrank', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Schuh', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'See', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'September',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Service', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Sessel', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Sohn', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Sommer', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Sonntag', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Spaß', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Spaziergang',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    {
      frage: 'Spielplatz',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Stempel', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Stock', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Stoff', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Strand', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Strom', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Student', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Stuhl', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Supermarkt',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Tag', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Teil', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Teller', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Teppich', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Termin', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Test', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Text', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Tipp', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Tisch', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Topf', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Tourist', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Turm', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Unfall', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Unterricht',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    {
      frage: 'Unterschied',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Urlaub', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Vater', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Verein', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Verkäufer',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Verkehr', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Vermieter',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Vertrag', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Vogel', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Vormittag',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Vorname', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Wagen', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Wald', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Weg', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Wein', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Westen', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Wetter', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Wind', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Winter', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    {
      frage: 'Wochentag',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 0,
    },
    { frage: 'Wunsch', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Zahn', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Zettel', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Zoll', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Zucker', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Zug', antworten: ['der', 'die', 'das'], richtigeAntwort: 0 },
    { frage: 'Ärztin', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Übernachtung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Abfahrt', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Adresse', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Ampel', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Angestellte',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Angst', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Ankunft', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Anmeldung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Anrede', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Ansage', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Antwort', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Anzeige', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Apotheke', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Arbeit', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Aufgabe', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Ausbildung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Auskunft', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Ausländerin',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Aussage', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Ausstellung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Autobahn', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Bäckerei', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Bahn', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Banane', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Bank', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Batterie', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Beamtin', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Bekannte', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Beratung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Berufsschule',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Bewerbung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Birne', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Bitte', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Blume', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Bluse', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Bohne', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Brücke', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Briefmarke',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Brieftasche',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Brille', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Butter', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'CD', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'CD-ROM', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Creme', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Dame', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Dauer', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Deutsche', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Disco', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Durchsage',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Dusche', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'E-Mail', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Ecke', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Ehefrau', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Einführung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Einladung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Eltern', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Entschuldigung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Erfahrung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Erlaubnis',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Ermäßigung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Erwachsene',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Fähre', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Führung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Fabrik', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Fahrkarte',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Familie', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Farbe', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Ferien', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Feuerwehr',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Firma', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Flasche', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Flur', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Frage', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Frau', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Freizeit', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Freundin', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Frist', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Gabel', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Garage', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Gebühr', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Geldbörse',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Gesamtschule',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Geschwister',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Gesundheit',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Größe', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Grippe', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Großeltern',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Großmutter',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Grundschule',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Gruppe', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Halbpension',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Halle', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Haltestelle',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Hand', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Hausaufgabe',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Hausfrau', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Heimat', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Heizung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Hilfe', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Hose', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Idee', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Industrie',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Information',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Jacke', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Jugendherberge',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Jugendliche',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Küche', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Kündigung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Kamera', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Kanne', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Karte', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Kartoffel',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Kasse', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Kassette', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Katze', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Kenntnisse',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Kette', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Kirche', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Klasse', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Kleidung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Kneipe', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Kollegin', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Kontrolle',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Kosmetik', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Krankenkasse',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Krankheit',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Kreditkarte',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Kreuzung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Kunde', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Kundin', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Lösung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Lampe', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Landschaft',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Lebensmittel',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Lehre', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Lehrerin', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Leute', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Luft', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Lust', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Mülltonne',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Maschine', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Mehrwertsteuer',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Meinung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Menge', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Miete', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Milch', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Minute', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Mitte', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Mitteilung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Mittelschule',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Mode', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Musik', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Mutter', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Nähe', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Nachbarin',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Nacht', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Natur', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Note', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Notiz', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Nudel', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Nummer', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Oma', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Operation',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Orange', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Ordnung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Panne', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Partei', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Partnerin',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Party', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Pause', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Pension', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Plastik', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Polizei', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Portion', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Post', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Postleitzahl',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Prüfung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Praxis', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Qualität', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Quittung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Raucherin',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Realschule',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Rechnung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Reinigung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Reise', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Reparatur',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Rezeption',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Rosé', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Rose', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'S-Bahn', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Sache', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Schülerin',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Scheckkarte',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Schokolade',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Schule', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Schwester',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'See', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Sehenswürdigkeit',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Seife', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Sekretärin',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Sekunde', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Sendung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Sonne', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Sorge', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Spülmaschine',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Speisekarte',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Sprache', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Sprachschule',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Sprechstunde',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Stadt', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Steuer', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Straße', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Straßenbahn',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Studentin',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Stunde', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Suppe', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Tür', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Tüte', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Tankstelle',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Tasche', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Tasse', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Tochter', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Toilette', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Tomate', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Treppe', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'U-Bahn', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Uhr', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Universität',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Unterhaltung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Unterkunft',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Unterschrift',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Untersuchung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Verbindung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Verkäuferin',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Versicherung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Verspätung',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Volksschule',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Vorsicht', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Vorwahl', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Wäsche', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Welt', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Werkstatt',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    {
      frage: 'Wirtschaft',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Woche', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Wohnung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Wolke', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Wurst', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Zahl', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Zeit', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Zeitschrift',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Zeitung', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    {
      frage: 'Zigarette',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 1,
    },
    { frage: 'Zitrone', antworten: ['der', 'die', 'das'], richtigeAntwort: 1 },
    { frage: 'Alter', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Angebot', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Appartement',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Auge', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Ausland', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Auto', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Büro', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Baby', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Bad', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Bein', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Beispiel', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Benzin', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Bett', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Bier', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Bild', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Blatt', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Blut', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Brötchen', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Brot', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Buch', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Cafe', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Dach', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Datum', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Ding', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Doppelzimmer',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Dorf', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Ei', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Einzelzimmer',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Eis', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Ende', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Erdgeschoss',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Ergebnis', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Essen', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Fahrrad', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Fax', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Fenster', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Fernsehgerät',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Fest', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Feuer', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Feuerzeug',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Fieber', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Fleisch', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Flugzeug', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Formular', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Foto', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Frühjahr', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Frühstück',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Fundbüro', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Gas', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Geburtsjahr',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    {
      frage: 'Gegenteil',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Geld', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Gemüse', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Gepäck', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Gericht', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Geschäft', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Geschenk', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Geschirr', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Gesicht', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Gespräch', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Getränk', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Gewicht', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Gewitter', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Glück', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Glas', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Gleis', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Guthaben', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Gymnasium',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Hähnchen', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Haar', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Handtuch', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Handy', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Haus', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Hemd', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Herz', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Hobby', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Holz', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Internet', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Jahr', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Junge', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Kennzeichen',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Kfz', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Kind', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Kino', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Kleid', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Konsulat', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Konto', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Konzert', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Laden', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Lager', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Land', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Leben', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Lebensmittel',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Leid', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Licht', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Lied', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Loch', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Lokal', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Mädchen', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Möbel', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Mal', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Material', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Medikament',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Meer', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Messer', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Metall', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Mittel', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Moment', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Morgen', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Museum', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Obst', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Orange', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Öl', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Päckchen', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Paket', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Papier', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Parfüm', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Plastik', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Praktikum',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Problem', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Programm', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Rücken', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Radio', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Rathaus', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Reifen', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Reis', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Reisebüro',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    {
      frage: 'Restaurant',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Rezept', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Rind', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Rosé', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Salz', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Schiff', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Schild', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Schloss', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Schwein', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Schwimmbad',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Service', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Sofa', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Sonderangebot',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Stück', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Standesamt',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Steuer', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Streichholz',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Studium', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Tag', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Taxi', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Teil', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Telefon', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Telefonbuch',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Theater', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Thema', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Ticket', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Tier', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Trinkgeld',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Video', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Wasser', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Werkzeug', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Wetter', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    {
      frage: 'Wiederhören',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    {
      frage: 'Wiedersehen',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    {
      frage: 'Wochenende',
      antworten: ['der', 'die', 'das'],
      richtigeAntwort: 2,
    },
    { frage: 'Wort', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Zentrum', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Zeugnis', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
    { frage: 'Zimmer', antworten: ['der', 'die', 'das'], richtigeAntwort: 2 },
  ];
  let spielIndex = Math.floor(Math.random() * fragen.length);

  function hideHome() {
    document.querySelector('.Home').classList.add('hide');
    document.querySelector('.Spiel').classList.remove('hide');
  }
  function pruefAntwort(antwortText) {
    const istRichtig =
      fragen[spielIndex].antworten.indexOf(antwortText) ===
      fragen[spielIndex].richtigeAntwort;
    if (istRichtig) {
      plusPunkt += 1;
      console.log('Hurra!');
      document.body.style.backgroundColor = '#22e358';
      document.querySelector('.ergebnissR').classList.remove('hidden');
    } else {
      minusPunkt += 1;
      console.log('AAAa!');
      document.body.style.backgroundColor = '#f65a5a';
      document.querySelector('.ergebnissF').classList.remove('hidden');
    }
    insFrage += 1;
    setTimeout(() => {
      spielIndex = Math.floor(Math.random() * fragen.length);
      document.body.style.backgroundColor = 'white';
      document.querySelector('.ergebnissR').classList.add('hidden');
      document.querySelector('.ergebnissF').classList.add('hidden');
    }, 750);
  }
  function resetScore() {
    insFrage = 0;
    plusPunkt = 0;
    minusPunkt = 0;
  }
</script>

<div class="App">
  <div class="container">
    <div class="Home">
      <h1>Das Artikelspiel</h1>
      <h2>Hallo!</h2>
      <p class="halloText">
        Das ist ein Spiel für Artikeltraininning. Nach "Beginn" öffnet ein
        Fenster, wo ein Wort und drei Artikeloptionen gibt. Jenach du korrekte
        Antwort aussuchst, erhöht die Zahl der "Rictige Antworte", beim falschen
        Auswahl ist es ganz umgekehrt. Näcstes Wort kommt automatisch eine
        Sekunde nach Auswahl und es gibt zurzeit 680+ Wörter. Wichtig ist
        allerdings nicht Punkte sammeln, sondern durch Übungen lernen.
        <br />
        Viel Spaß dabei!
      </p>
      <div class="beginnWrap">
        <button class="beginn" on:click={hideHome}>Beginn</button>
      </div>
    </div>
    <div class="Spiel hide">
      <div class="uebersicht">
        <Punkte
          insFragen={insFrage}
          plusPunkte={plusPunkt}
          minusPunkte={minusPunkt}
        />
      </div>
      <div class="ergebniss">
        <div class="ergebnissRwrap">
          <h2 class="ergebnissR hidden">✓ Korrekt!</h2>
        </div>
        <div class="ergebnissFwrap">
          <h2 class="ergebnissF hidden">✘ Falsch!</h2>
        </div>
      </div>
      <Frage frageText={fragen[spielIndex].frage} />
      <div class="antworten">
        <Antworten
          antwortText={fragen[spielIndex].antworten[0]}
          {pruefAntwort}
        />
        <Antworten
          antwortText={fragen[spielIndex].antworten[1]}
          {pruefAntwort}
        />
        <Antworten
          antwortText={fragen[spielIndex].antworten[2]}
          {pruefAntwort}
        />
      </div>
      <div class="reset-btn-wrap">
        <input
          type="image"
          on:click={resetScore}
          class="reset-btn"
          src="./img/Reset.png"
          height="50"
          width="50"
          alt="Reset Button"
        />
      </div>
    </div>
  </div>
</div>

<style>
  *,
  *::before,
  *::after {
    box-sizing: border-box;
    font-family: 'Roboto', sans-serif;
  }

  :global(body) {
    background-color: white;
  }

  .App {
    width: 100%;
    height: 100%;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: white;
  }

  .hide {
    display: none;
  }

  .hidden {
    opacity: 0;
  }

  .container {
    padding: 2vw;
    width: 800px;
    max-width: 90%;
  }
  .halloText {
    line-height: 1.5;
  }

  .beginnWrap {
    margin-top: 40px;
    text-align: center;
  }
  .beginn {
    padding: 10px 20px;
    border-radius: 5px;
    font-size: 24px;
    font-weight: bold;
    background-color: limegreen;
    color: white;
  }

  div.uebersicht {
    margin: 0 auto;
    display: block;
    text-align: center;
    max-width: 233px;
    height: 100px;
    border: 1px solid white;
    box-shadow: 0 4px 4px rgba(0, 0, 0, 25%);
  }

  .ergebnissRwrap {
    position: absolute;
    left: 50%;
    margin-left: -54px;
    margin-top: 10px;
    color: #22e358;
  }
  .ergebnissFwrap {
    position: absolute;
    left: 50%;
    margin-left: -47px;
    margin-top: 10px;
    color: #f65a5a;
  }

  div.antworten {
    text-align: center;
  }

  .reset-btn-wrap {
    text-align: center;
  }
  .reset-btn {
    border: none;
    margin: 100px 10px 10px;
  }
</style>
