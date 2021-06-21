# java
Name:game Little

private void _Click(object sender, EventArgs e)
		{	if (GameStatus == GameStatus.Continue)		{
				Me me = (BirdBox)sender;

			if (me != null && me.Status != "Dead")
			{
					PlayBirdHitSound();
					birdbox.Status = "Dead";
				birdbox.Image.RotateFlip(RotateFlipType.Rotate270FlipNone);
					Me.Image = Properties.Resources.explosion_animation;
				}
				else
				{
					PlayGunSound();
				}
			}
		}
		
		private void PlayGameForm_Click(object sender, EventArgs e)
		{
			if (GameStatus == GameStatus.Continue)
			{
				PlayGunSound();
			}
		}		

		private void RemoveBird(BirdTimer BirdTimer)	{
			if (BirdTimer != null)
			{
				FlyingBirds.Remove(BirdTimer);

				BirdTimer.Stop();
				BirdTimer.BirdBox.Dispose();
				BirdTimer.Dispose();
			}
		}
 

