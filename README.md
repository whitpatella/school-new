# school-new
CREATE TABLE school_hours
    (id INTEGER PRIMARY KEY AUTOINCREMENT,
    subject TEXT,
    hours_required INTEGER, 
    hours_completed INTEGER);

INSERT INTO school_hours(id, subject, hours_required, hours_completed) VALUES (1, "math", 160, 12.5);
INSERT INTO school_hours(id, subject, hours_required, hours_completed) VALUES (2, "english", 160, 13.5);
INSERT INTO school_hours(id, subject, hours_required, hours_completed) VALUES (3, "history", 160, 13);
INSERT INTO school_hours(id, subject, hours_required, hours_completed) VALUES (4, "science", 160, 14);
INSERT INTO school_hours(id, subject, hours_required, hours_completed) VALUES (5, "coding", 130, 8.5);
INSERT INTO school_hours(id, subject, hours_required, hours_completed) VALUES (6, "piano", 130, 12);
INSERT INTO school_hours(id, subject, hours_required, hours_completed) VALUES (7, "violin", 120, 8);
INSERT INTO school_hours(id, subject, hours_required, hours_completed) VALUES (8, "french", 120, 8);
INSERT INTO school_hours(id, subject, hours_required, hours_completed) VALUES (9, "baking", 120, 24);
INSERT INTO school_hours(id, subject, hours_required, hours_completed) VALUES (10, "pe", 120, 9.5);
INSERT INTO school_hours(id, subject, hours_required, hours_completed) VALUES (11, "organ", 120, 3);

SELECT *, (hours_required - hours_completed) AS "hours_remaining" FROM school_hours;
SELECT hours_required, subject FROM school_hours GROUP BY subject ORDER BY hours_required; 
SELECT subject, (hours_required - hours_completed) AS "hours_remaining" FROM school_hours WHERE hours_completed < (hours_required - hours_completed) AND hours_required > hours_completed ORDER BY subject;

SELECT SUM(hours_required) FROM school_hours 
