import { put } from '@vercel/blob';
import { randomUUID } from 'node:crypto';

export const config = { api: { bodyParser: false } };

export default async function handler(req, res) {
  if (req.method !== 'POST') return res.status(405).json({ error: 'method' });
  const chunks = [];
  for await (const c of req) chunks.push(c);
  const buf = Buffer.concat(chunks);
  if (!buf.length || buf.length > 4.4e6) return res.status(400).json({ error: 'size' });
  try {
    const id = randomUUID();
    const blob = await put(`gradua2s/${id}.jpg`, buf, {
      access: 'public',
      contentType: 'image/jpeg',
      addRandomSuffix: false,
    });
    res.status(200).json({ id, url: blob.url });
  } catch (e) {
    res.status(500).json({ error: 'storage' });
  }
}
