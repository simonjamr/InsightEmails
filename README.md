# InsightEmails
Information and SP about the various emails sent out from Insight
SELECT
   GP.Surname
   ,GP.Initials
   ,GP.GPPC
   ,P.[Practice Name]
   ,gp.PCG
   ,gp.Status 
   ,GPS.SectorName AS GPSectorName
FROM GP
       LEFT JOIN  [General Medical Practice] AS P ON GP.GPPC = P.[Practice Code]
       LEFT JOIN  refGPSector AS GPS ON GP.SectorID = GPS.SectorID
WHERE gp.pcg = '03N' 
       AND  gp.Status = 'A'
ORDER BY
       P.[Practice Name],
       Surname,
       Initials
